require 'fssm'

desc "Watch the current project for changes"
task :watch do
  
  # Change these if you have renamed your 'source' and 'public' directories
  SRC  = "source"
  DEST = "public"
  
  def compile(relative, action)

    file_extension = File.extname(relative)
    file_name = File.basename(relative, file_extension)
    file_path = File.dirname(relative).sub(/(scss|sass)/, 'css')
        
    # Let the user know what's going on.
    if action == :create
      puts "New file: #{relative}\n>>> Added"
    elsif action == :delete
      puts "File deleted: #{relative}\n>>> Removed"
    else
      puts "Change detected to: #{relative}\n>>> Recompiled"
    end
    
    # Make any necessary changes to the destination files.
    if action == :delete

      # Remove the appropriate file.
      if file_extension == ".sass" || file_extension == ".scss"
        if File.exists?("#{DEST}/#{file_path}/#{file_name}.css")
          `rm #{DEST}/#{file_path}/#{file_name}.css`
        end
      elsif file_extension == ".coffee"
        if File.exists?("#{DEST}/#{file_path}/#{file_name}.js")
          `rm #{DEST}/#{file_path}/#{file_name}.js`
        end
      else
        if File.exists?("#{DEST}/#{file_path}/#{file_name}#{file_extension}")
          `rm #{DEST}/#{file_path}/#{file_name}#{file_extension}`
        end
      end

      # Also remove the directory if there's nothing else there.
      if (Dir.entries("#{DEST}/#{file_path}") - %w{ . .. }).empty?
        `rmdir #{DEST}/#{file_path}`
      end

    else

      # Make sure the directory exists for the file
      unless File.exists?("#{DEST}/#{file_path}")
        `mkdir #{DEST}/#{file_path}`
      end

      # Compile the file
      if file_extension == ".sass"
        `sass --line-numbers #{SRC}/#{relative} #{DEST}/#{file_path}/#{file_name}.css`
        `sass --line-numbers #{SRC}/sass/style.sass #{DEST}/css/style.css`
      elsif file_extension == ".scss"
        `sass --scss --line-numbers #{SRC}/#{relative} #{DEST}/#{file_path}/#{file_name}.css`
        `sass --scss --line-numbers #{SRC}/scss/style.scss #{DEST}/css/style.css`
      elsif file_extension == ".haml"
        `haml #{SRC}/#{relative} #{DEST}/#{file_path}/#{file_name}.html`
      elsif file_extension == ".coffee"
        `coffee --compile --output #{DEST}/#{file_path} #{SRC}/#{relative}`
      else
        `cp #{SRC}/#{relative} #{DEST}/#{file_path}/#{file_name}#{file_extension}`
      end

    end
  end

  # Punch it, Chewy!
  puts ">>> Watching for changes"

  FSSM.monitor("#{Dir.pwd}/#{SRC}", '**/*') do
    create {|base, relative| compile(relative, :create)}
    update {|base, relative| compile(relative, :update)}
    delete {|base, relative| compile(relative, :delete)}
  end


end
