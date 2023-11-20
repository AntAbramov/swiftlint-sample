# Example of configured swiftlint file
<p align="center">
    <a href="https://github.com/realm/SwiftLint">
    		<img src="https://img.shields.io/badge/SwiftLint_GitHub-repository-orange" alt="GitHub repository">
    </a>
    <a href="LICENSE">
        <img src="https://img.shields.io/badge/license-MIT-brightgreen.svg" alt="MIT License">
    </a>
  	<a href="https://realm.github.io/SwiftLint/rule-directory.html">
        <img src="http://img.shields.io/badge/read_the-docs-2196f3.svg" alt="Documentation">
</p>

This repository provides a generic SwiftLint configuration file that can be used by anyone to write clean and readable code using the Swift programming language, without deep-diving into the configuration itself.

It is a good way to improve the quality of your code, as well as to learn new swift language tips.

If you think a rule (opt_in or custom) should be in this generic SwiftLint file, send a pull request with suggestions.

## Installation 

### Using [Homebrew](https://brew.sh):

Homebrew is a free and open-source software package management system that simplifies the installation of software on Apple's OS

1. Install homebrew
   Run installation script in terminal, then enter the password

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. Install SwiftLint via homebrew:

```bash
brew install swiftlint
```

3. Open project folder and add swiftlint.yml file from this repository there
4. Then you need to add Build Phase in Xcode, that will automaticly run swiftlint every time you'll build your project
   Open Xcode -> Project Settings -> Target -> Build Phases Tab -> Add new build phase -> New Run Script Phase -> Rename in into Swiftlint -> Expand Script -> Replace green comment with:

```bash
export PATH="$PATH:/opt/homebrew/bin"
if which swiftlint > /dev/null; then
  swiftlint
else
  echo "warning: SwiftLint not installed, download from https://github.com/realm/SwiftLint"
fi
```

### Warning: If your Xcode version is greater than 15.0:

You need go to Build Settings tab -> find 'User Script Sandboxing' setting and change its property to 'No'
