# Sorting Folder

This is a Python script that sorts files in a specified folder based on their file extensions. It uses multithreading to improve performance when handling large folders.

## Usage

The script can be executed with the following command-line arguments:

```
python sort_folder.py [-h] [--source SOURCE] [--output OUTPUT]
```

- `--source`, `-s`: Specifies the source folder to be sorted. Default value is "TestFolder".
- `--output`, `-o`: Specifies the output folder where the sorted files will be placed. Default value is "dist".

## Dependencies

The script requires the following dependencies:

- `argparse`: Used for parsing command-line arguments.
- `pathlib`: Provides an object-oriented interface to filesystem paths.
- `shutil`: Used for file copying.
- `queue`: Implements a thread-safe queue.
- `threading`: Provides high-level threading interfaces.
- `logging`: Used for logging messages during the sorting process.

## Sorting Process

The script follows the following steps to sort the files:

1. Parse the command-line arguments to determine the source and output folders.
2. Use a recursive function to grab all the subfolders within the source folder.
3. Create a separate thread for each file extension found in the source folder.
4. Each thread waits until all subfolders have been grabbed before starting the sorting process.
5. Each thread handles its assigned file extension by creating a corresponding folder in the output directory and copying the files with that extension.
6. Once all threads have finished processing, the script completes.

## Example

To sort files in the "TestFolder" directory and place the sorted files in the "dist" directory, you can run the script with the following command:

```
python sort_folder.py --source TestFolder --output dist
```

## Note

Before deleting the old folder, ensure that the sorting process has completed successfully and that the files have been copied to the desired output folder.

Please feel free to modify and adapt this script according to your needs.
