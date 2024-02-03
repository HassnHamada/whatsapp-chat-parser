# WhatsApp Chat Parser

## Introduction
WhatsApp Parser is a tool designed to simplify the process of parsing text data extracted from WhatsApp conversations. It aims to provide users with an easy-to-use interface for extracting meaningful information from chat logs, such as timestamps, sender names, and messages.

```
pip install whatsapp-parse
```

## Features
- Extract conversation data including date, time, sender, and message content.  
- Parse chat logs into a Pandas DataFrame
- Directly output a CSV file from the command line.


## Usage
### From the command line
Required input:

- WhatsApp chat file. 

Optional flags:

- -e : To specify the encoding. (Defaults to `UTF-8`)
- -o : Specifies the output directory where the parsed CSV will be saved. (Default to the same as input file. `/path/to/file/filename.txt` to `/path/to/file/filename.csv`)  
- -t : The maximum amount of time between two messages in seconds to be considered a part of the same conversation. In case you don't want to group messages, input '0'. (Default to 300 seconds)

Example Run: 

```
python parser.py '/friends/WhatsApp Chat with friend_1.txt' 
```

This will parse the `/friends/WhatsApp Chat with friend_1.txt` file and save the CSV file to `/friends/WhatsApp Chat with friend_1.csv`.

```
python parser.py '/friends/WhatsApp Chat with friend_2.txt' -o '/output.csv'  
```

This will parse the `/friends/WhatsApp Chat with friend_2.txt` file and save the CSV file to `/output.csv`.


### From a script

When running another python script you can read the WhatsApp file as a list of strings. Then pass it to the function `chat_to_dataframe` this will return a Pandas DataFrame.

```python
file_path = '/friends/WhatsApp Chat with friend_3.txt'
with open(file_path, 'r', encoding='utf-8') as f:
    text = f.readlines()  
df = chat_to_dataframe(text)
```


## Future Updates
- Support for additional date and time formats. 
- Add more output formats.
- Add media attachments handling.

## Contributing
We welcome contributions to the WhatsApp Chat Parser project. If you have suggestions or improvements, please open an issue or submit a pull request.


## Contact
For any questions or feedback, please contact me **Hassn Hamada** at hassneltokhy4@gmail.com.
