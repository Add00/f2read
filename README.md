# F2Read / Usage
**This command line interface tool will help you to read 1 or multiple files and convert the contents into a READMe.md file explaining your code.**

<br>

![alt text](https://github.com/cduarte3/f2read/blob/main/images/render.gif?raw=true)

<br>

# Initial Setup
**To run the CLI interface, Ollama has to be installed to the system. This Tool runs off the Ollama provider, using any model of a user's choosing. By default the model will be set to Gemma2.**

## Steps

1. **Install the Ollama environment.**<br>
    - This can be done by visiting https://ollama.com and following the download instructions. <br><br> ![alt text](https://github.com/cduarte3/f2read/blob/main/images/image.png?raw=true)

<br><br>

2. **Select the model of your choosing.**<br>
    - Visit the models tab, or https://ollama.com/library, and choose a model that works for you. By default this tool uses Gemma2, you may choose that if you so wish. <br><br> ![alt text](https://github.com/cduarte3/f2read/blob/main/images/image-1.png?raw=true)

<br><br>

3. **Use the run command to start the model.**<br>
    - Open up a cmd prompt window and use the run command for the model of your choice. <br><br> **Example for Gemma2:** <br><br> ![alt text](https://github.com/cduarte3/f2read/blob/main/images/image-3.png?raw=true) <br><br> **Usage:** <br><br> ![alt text](https://github.com/cduarte3/f2read/blob/main/images/image-4.png?raw=true)

<br><br>

4. **Pull the repo and get files ready.**<br>
    - Once Ollama model is set up, clone or fork the repo and place any of your files inside the src folder or in the root folder (file names will need to be called with a prefix of ./ if placed in the root)
.
<br><br>

5. **Good to go.**<br>
    - Once these steps have been completed and the model is running, you may run the command line interface tool. The commands and usage guide will be listed below.

    - To check if your Ollama model is running, type the command ```ollama ps```. <br><br>**Example of usage:** <br><br>![alt text](https://github.com/cduarte3/f2read/blob/main/images/image-5.png?raw=true)

<br><br>

# Commands
**Listed below are the commands that can be used to interact with the F2Read tool.**<br><br>

## CLI Tool

### f2 <fl...>
- ```bun f2 fileName```
> <br>Running f2 with a following path to a file name will pass in the file and use the tool.<br><br>
**NOTE: If you are passing in a file, for example main.py, the tool will assume it is inside the src folder. Typing a dir name before the filename will also work, for example: 'examples/sample.py' which exists at 'f2read/src/examples/sample.py'. If filename has no path, program will check in src folder by default.**<br><br>

### f2 <dir...>
- ```bun f2 dirName```
> <br>Running f2 with a directory name will pass in the directory and read all its files.<br><br>
**NOTE: If you are passing in a directory, for example 'examples/', the tool will assume it is inside the src folder. Any dir name outside of src will not work, the program will check in src folder by default.**<br><br>

### --output filePath OR --o filePath
- ```bun f2 fileName --output filePath.md```
> <br>Adding the --output or --o tag as an option in the CLI call will allow for renaming of the output markdown file to the specified filename. File must be specified with .md<br><br> If README.md is not an issue for a file name, DO NOT include this tag<br><br>

### --model modelName OR --m modelName
- ```bun f2 fileName --model llama2```
> <br>Adding the --model or --m tag as an option in the CLI call will allow for specifying the model to be used for the prompt. Model must be a valid Ollama model to work.<br><br> If Gemma2 / Gemma2:2b is not an issue for a prompt model, DO NOT include this tag<br><br>

<br>

## Version
- ```bun f2 --v OR bun f2 --version```
> <br>Will return the current version of the CLI tool being used.<br><br>

<br>

## Help
- ```bun f2 --h OR bun f2 --help```
> <br>Will reload this message. Any future commands or changes will be reflected here above.<br><br>

<br>

## Example 1
- ```bun f2 main.py```
> <br>Produces a README.md file explaining the contents of main.py from the src folder<br><br>

## Example 2
- ```bun f2 examples/sample.py```
> <br>Produces a README.md file explaining the contents of sample.py from the src/exmples/ folder<br><br>

## Example 3
- ```bun f2 examples/```
> <br>Produces a README.md file explaining the contents of each file found inside of the src/examples/ folder<br><br>

<br>

# Config

If you would like to have your commands loaded automatically through a configuration file, follow these steps:

 ## 1. Create a configuration file

Go to your home directory and create a new file in there called F2READ-config.toml. Format it something like this:

```
model = "llama3.2"
output = "NAME.md"
tokenUsage = false
stream = true
```

It can contain variables of only the above: model, output, tokenUsage, and stream. They can be written in any order.

## 2. Enjoy

The program should take these values from your configuration file and use them. This way you don't have to type them on the command line each time.
