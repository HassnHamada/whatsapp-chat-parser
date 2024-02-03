## Usage From the command line
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


## Usage from a script

When running another python script you can read the WhatsApp file as a list of strings. Then pass it to the function `chat_to_dataframe` this will return a Pandas DataFrame.

```python
file_path = '/friends/WhatsApp Chat with friend_3.txt'
with open(file_path, 'r', encoding='utf-8') as f:
    text = f.readlines()  
df = chat_to_dataframe(text)
```


