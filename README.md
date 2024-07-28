
- [CMake official Tutorial Site](https://cmake.org/cmake-tutorial/)

### Table of Contents

1. **Introduction to CMake**
   - What is CMake?
   - Benefits of Using CMake
   - Installing CMake

2. **Setting Up Your Environment**
   - Installing CMake on Different Operating Systems
   - Verifying the Installation

3. **Basic Project Structure**
   - Creating a Simple Project
   - Understanding the Directory Layout

4. **Creating a CMakeLists.txt File**
   - Basic Structure of CMakeLists.txt
   - Specifying the Minimum Required Version
   - Project Declaration

5. **Adding Source Files**
   - Adding Executable Targets
   - Organizing Source and Header Files

6. **Configuring Build Options**
   - Setting Compiler Flags
   - Defining Build Types (Debug, Release)

7. **Building the Project**
   - Running CMake to Generate Build Files
   - Compiling the Project with Make, Ninja, or Other Generators

8. **Advanced CMake Features**
   - Using Variables and Cache Variables
   - Configuring Include Directories and Linker Settings

9. **Handling Dependencies**
   - Finding and Using External Libraries
   - Using `find_package` and `include_directories`

10. **CMake and IDEs**
    - Integrating CMake with Popular IDEs (Visual Studio, CLion, etc.)

11. **Testing with CMake**
    - Adding Tests to Your Project
    - Using CTest for Testing

12. **Packaging with CMake**
    - Installing Targets
    - Creating a Distribution Package

13. **Best Practices and Tips**
    - Organizing Large Projects
    - Common Pitfalls and How to Avoid Them

14. **Conclusion**
    - Recap
    - Further Reading and Resources

---
---

### Introduction to CMake

**What is CMake?**<br>
CMake is an **open-source, cross-platform family of tools designed to build, test, and package software**. It is used to control the software **compilation process** using simple platform and compiler-independent configuration files.

**Benefits of Using CMake:**
- **Portability:** Write once, build anywhere.
- **Flexibility:** Supports various build tools like Make, Ninja, etc.
- **Scalability:** Handles projects of all sizes.
- **Integration:** Works well with IDEs and other development tools.

**Installing CMake:**
- **On Windows:** Download and run the installer from the CMake website.
- **On macOS:** Use Homebrew with *`brew install cmake`.*
- **On Linux:** Use your distribution's package manager, e.g., *`sudo apt-get install cmake`.*

### Setting Up Your Environment

**Installing CMake on Different Operating Systems:**

- **Windows:**
  1. Go to the [CMake download page](https://cmake.org/download/).
  2. Download the installer for Windows.
  3. Run the installer and follow the instructions.

- **macOS:**
  1. Open a terminal.
  2. Install Homebrew if you haven't already: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
  3. Install CMake: `brew install cmake`

- **Linux:**
  - On Ubuntu/Debian:
    ```sh
    sudo apt-get update
    sudo apt-get install cmake
    ```
  - On Fedora:
    ```sh
    sudo dnf install cmake
    ```

**Verifying the Installation:**
After installation, verify that CMake is correctly installed by running:
```sh
cmake --version
```
You should see the version number of CMake printed to the terminal.

### Basic Project Structure

Let's start with a simple project structure. We'll create a "Hello, World!" project in C.

**Directory Layout:**
```
HelloWorld/
├── CMakeLists.txt
├── src/
│   └── main.c
└── include/
    └── hello.h
```

- `CMakeLists.txt`: The main configuration file for CMake.
- `src/`: Directory containing source files.
- `include/`: Directory containing header files.

### Creating a CMakeLists.txt File

**Basic Structure of CMakeLists.txt:**

Create a file named `CMakeLists.txt` in the root of your project directory with the following content:

```cmake
cmake_minimum_required(VERSION 3.10)

# Set the project name
project(HelloWorld)

# Add an executable
add_executable(hello src/main.c)
```

### Adding Source Files

**Adding Executable Targets:**

Create a directory named `src` and a file named `main.c` inside it with the following content:

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

### Configuring Build Options

**Setting Compiler Flags:**
You can set compiler flags using the `target_compile_options` command in your `CMakeLists.txt` file:

```cmake
target_compile_options(hello PRIVATE -Wall -Wextra -Wpedantic)
```

### Building the Project

**Running CMake to Generate Build Files:**

1. Open a terminal and navigate to your project directory.
2. Create a build directory: `mkdir build && cd build`
3. Run CMake to generate the build files: `cmake ..`
4. Compile the project: `make` (or `cmake --build .` if using another generator)

### Advanced CMake Features

**Using Variables and Cache Variables:**

You can define and use variables in your `CMakeLists.txt` file:

```cmake
set(SOURCE_FILES src/main.c)
add_executable(hello ${SOURCE_FILES})
```

### Handling Dependencies

**Finding and Using External Libraries:**

You can use the `find_package` command to locate and use external libraries. For example, to use the Boost library:

```cmake
find_package(Boost REQUIRED)
include_directories(${Boost_INCLUDE_DIRS})
```

### CMake and IDEs

**Integrating CMake with Popular IDEs:**

Most modern IDEs support CMake natively. For example, in CLion, simply open the project directory, and CLion will automatically detect the CMake configuration.

### Testing with CMake

**Adding Tests to Your Project:**

You can add tests using the `add_test` command. For example:

```cmake
enable_testing()
add_test(NAME HelloTest COMMAND hello)
```

### Packaging with CMake

**Installing Targets:**

You can specify installation rules in your `CMakeLists.txt` file:

```cmake
install(TARGETS hello DESTINATION bin)
```

### Best Practices and Tips

**Organizing Large Projects:**

For larger projects, it is a good practice to split the project into multiple directories and use `add_subdirectory` to include them.

```cmake
add_subdirectory(src)
add_subdirectory(include)
```

**Common Pitfalls and How to Avoid Them:**

- Always specify the minimum required version of CMake.
- Use relative paths cautiously.
- Keep your `CMakeLists.txt` modular and well-organized.

### Conclusion

**Recap:**
We have covered the basics of setting up a CMake project, adding source files, configuring build options, and handling dependencies. We've also touched on advanced features and best practices.

**Further Reading and Resources:**
- [CMake Documentation](https://cmake.org/documentation/)
- [Mastering CMake](https://www.amazon.com/Mastering-CMake-Ken-Martin/dp/1930934122)
- [CMake by Example](https://www.jetbrains.com/help/clion/quick-cmake-tutorial.html)

---

Let's start with creating your first CMake project.

### Step-by-Step Project Creation

1. **Create Project Directory:**
   ```sh
   mkdir HelloWorld
   cd HelloWorld
   ```

2. **Create Directory Structure:**
   ```sh
   mkdir src include
   ```

3. **Create `CMakeLists.txt`:**
   ```sh
   touch CMakeLists.txt
   ```

4. **Edit `CMakeLists.txt`:**
   ```cmake
   cmake_minimum_required(VERSION 3.10)
   project(HelloWorld)
   add_executable(hello src/main.c)
   ```

5. **Create `main.c`:**
   ```sh
   touch src/main.c
   ```

6. **Edit `main.c`:**
   ```c
   #include <stdio.h>

   int main() {
       printf("Hello, World!\n");
       return 0;
   }
   ```

7. **Build the Project:**
   ```sh
   mkdir build
   cd build
   cmake ..
   make
   ```

8. **Run the Executable:**
   ```sh
   ./hello
   ```

Congratulations! You've successfully created and built your first CMake project.