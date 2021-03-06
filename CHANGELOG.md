<!-- usage documentation: http://expeditor-docs.es.chef.io/configuration/changelog/ -->

# win32-dir Changelog

<!-- latest_release -->
<!-- latest_release -->
<!-- release_rollup -->
<!-- release_rollup -->
<!-- latest_stable_release -->
## [win32-dir-0.7.2](https://github.com/chef/win32-dir/tree/win32-dir-0.7.2) (2020-11-30)

#### Merged Pull Requests
- Fix version management in expeditor / cache test runs [#30](https://github.com/chef/win32-dir/pull/30) ([tas50](https://github.com/tas50))
<!-- latest_stable_release -->

## [win32-dir-0.7.1](https://github.com/chef/win32-dir/tree/win32-dir-0.7.1) (2020-11-30)

#### Merged Pull Requests
- Add a super basic test pipeline in buildkite [#26](https://github.com/chef/win32-dir/pull/26) ([tas50](https://github.com/tas50))
- Require Ruby 2.4 or later [#27](https://github.com/chef/win32-dir/pull/27) ([tas50](https://github.com/tas50))
- Fix segfault if high-entropy 64-bit ASLR is enabled [#28](https://github.com/chef/win32-dir/pull/28) ([GabrielNagy](https://github.com/GabrielNagy))

## [win32-dir-0.6.4](https://github.com/chef/win32-dir/tree/win32-dir-0.6.4) (2020-08-17)

#### Merged Pull Requests
- Optimize requires for non-omnibus installs [#25](https://github.com/chef/win32-dir/pull/25) ([tas50](https://github.com/tas50))

## [win32-dir-0.6.3](https://github.com/chef/win32-dir/tree/win32-dir-0.6.3) (2018-12-31)

#### Merged Pull Requests
- Resolve chefstyle warnings [#22](https://github.com/chef/win32-dir/pull/22) ([tas50](https://github.com/tas50))
- Move version into its own ruby file [#23](https://github.com/chef/win32-dir/pull/23) ([tas50](https://github.com/tas50))

## [win32-dir-0.6.1](https://github.com/chef/win32-dir/tree/win32-dir-0.6.1) (2018-12-31)

#### Merged Pull Requests
- Fix the version bumping via expeditor [#21](https://github.com/chef/win32-dir/pull/21) ([tas50](https://github.com/tas50))

## [win32-dir-0.6.0](https://github.com/chef/win32-dir/tree/win32-dir-0.6.0) (2018-12-31)

#### Merged Pull Requests
- Require Ruby 2.2 and only ship required libs [#20](https://github.com/chef/win32-dir/pull/20) ([tas50](https://github.com/tas50))
- This gem is now maintained by Chef Software and released using our Expeditor tooling
- The master branch is now the default release branch once again
- Add new rake tasks for debugging
- Added the Chef code of conduct to the repo
- The readme and changelog are now in markdown format
- Code signing of the gem has been removed

## 0.5.1 - 20-Oct-2015
* The gem is now signed.
* The Rakefile gem tasks now assume Rubygems 2.x.
* Added a win32-dir.rb file for convenience.

## 0.5.0 - 15-Oct-2014
* Fixed an encoding error in an error message in the Dir.read_junction method.
  Thanks go to topac for the spot and patch.
* Replaced File.exists? with File.exist? in the test suite to avoid warnings
  in Ruby 2.1 and later.
* Do not let the version number fool you, this is not a major release. I
  simply ran out of version numbers.

## 0.4.9 - 2-Jul-2014
* Fixed the INVALID_FILE_ATTRIBUTES constant. It's only a 32-bit value.
  Thanks go to Ethan Brown for the patch.
* Use relative_require instead of manually doing things.
* Removed rubyforge_project from gemspec.
* Added a string_check to the Dir.junction? method.

## 0.4.8 - 27-Apr-2014
* More closely mimic Ruby's stringiness checks for overrided methods.

## 0.4.7 - 26-Apr-2014
* All arguments to methods are now interpolated so that they'll use whatever
  to_str implemenation the argument provides instead of assuming String
  arguments. This change was made because it turns out that at least some
  of the overridden methods in MRI accept Pathname objects. Thanks go to
  Josh Cooper/Puppet Labs for the spot.
* Refactored the Dir.getwd method to use bonafide FFI buffers instead of
  naked Ruby char buffers.
* Internally various functions now fail in the event that the resulting
  paths would exceed their buffers.

## 0.4.6 - 21-Oct-2013
* Fixed the INVALID_HANDLE_VALUE and INVALID_FILE_ATTRIBUTES constants for
  64-bit versions of Ruby.
* Added Rake as a development dependency.

## 0.4.5 - 23-Sep-2013
* Yet another encoding fix, this time one that affected JRuby.
* Fixed the Dir[] and Dir.glob methods so they match the spec. Thanks go
  to Chris Westbrook for the spot.

## 0.4.4 - 22-Sep-2013
* Yet another encoding fix. Thanks go to Rob Reynolds for the patch.

## 0.4.3 - 24-Jul-2013
* Changed the Dir.read_junction and CSIDL constant strings so that they
  use the default external encoding instead of UTF-16LE. This means that
  they will now work with methods like File.join. Thanks go to Josh Cooper
  for the patches.
* Some changes for internal handling of making FFI functions private.
* Updated gem:create task for rubygems 2.

## 0.4.2 - 8-Apr-2013
* Fixed the HANDLE function prototypes in the underlying FFI code and added
  some custom typedefs for convenience. This affects 64 bit Ruby code.

## 0.4.1 - 2-Oct-2012
* Added the Dir.read_junction method. Thanks go to Gabriel Wilkins for the patch.

## 0.4.0 - 29-Jun-2012
* Conversion to FFI. Should work with JRuby now.
* If current versions of Dir::XXX constant values cannot be found
  then default values are tried.
* Now requires Ruby 1.9 or later.

## 0.3.7 - 18-Jul-2010
* Modified Dir.glob and Dir[] to handle backslashes in path names.
* Added tests for the modified Dir.glob and Dir[] behavior.
* Removed the old non-gem install Rake task.

## 0.3.6 - 6-Feb-2010
* Bug fixes for Ruby 1.9.x. Thanks go to Kendall Gifford for the spot and
  the patch.
* Minor refactoring of the Dir.create_junction method. This fixed a bug for
  Ruby 1.9.x, but was also a little cleaner in general.
* Some Rakefile task and gemspec updates.

## 0.3.5 - 6-Aug-2009
* Changed the license to Artistic 2.0.
* Updated the gemspec, including the addition of a license attribute and
  test-unit as a development dependency.

## 0.3.4 - 5-May-2009
* Redefined the Dir.getwd (and the Dir.pwd alias) to always return a
  normalized path.
* Some gemspec updates.

## 0.3.3 - 30-Mar-2009
* Virtual folders like Dir::CONTROL, which were previously almost always nil,
  are now set to their display name.
* Fixed a bug in the create_junction method.
* Added an 'example' rake task to run the example code.
* Renamed the example program from dir_test.rb to dir_example.rb to prevent
  any potential confusion that it's a genuine test file.

## 0.3.2 - 25-Jul-2007
* Added a Rakefile with tasks for testing and installation.
* Removed the install.rb file (the Rakefile handles installation).
* Minor updates the README, MANIFEST, and test file.

## 0.3.1 - 16-Oct-2006
* Added the Dir.empty? method.
* Changed the Dir.reparse_dir? method to Dir.junction? (but kept an alias
  for backwards compatibility).
* Added rdoc for Dir.junction? (oops).
* Some test tweaks and additions.

## 0.3.0 - 28-May-2006
* Now pure Ruby.
* Now has a gem.
* Added a VERSION constant.

## 0.2.0 - 27-Jun-2005
* Added the Dir.create_junction and Dir.reparse_dir? methods.
* Added corresponding tests and documentation.

## 0.1.0 - 25-Feb-2005
* Initial release