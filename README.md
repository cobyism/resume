# Uberresumé

So today I started hacking together a HTML resume for myself, and I thought I might open-source it for others to use too. It's a work in progress, but when I've finished it for myself I'll make a point of putting it together with a nicer installer/usage.

At the moment:

```sh
$ git clone git://github.com/cobychapple/uberesume.git
$ cd uberesume
$ rake watch
```

Then edit the HAML and Sass files in the `source` directory to your heart's content. The `public` directory will (as long as you're running `rake watch`) then contain the compiled HTML and CSS versions of your resumé.

Enjoy!

## License

Copyright 2011 Coby Chapple.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
