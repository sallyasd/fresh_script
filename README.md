# fresh_script

This program will search for spotify tracks posted in the HipHopHeads subreddit and add them to a playlist of your choice. HipHopHeads is a subreddit dedicated to everything hiphop, including the latest mixtapes, videos, news, and anything else hip hop related from your favorite artists.

## Getting Started

### Prerequisites

This project uses Python3. You will need to setup a Spotify developer account and register your app. You will need the following things for this code:
* client id
* client secret
* your spotify username
* playlist id of the playlist you want to add the tracks to
* the url you want to redirect to for authentication, i.e. http://google.com/
 You will also need to setup a reddit instance with praw. [Heres](https://pythonforengineers.com/build-a-reddit-bot-part-1/) a useful guide I used to do this. 
```
pip3 install praw
pip3 install spotipy
pip3 install configparser
```

### Running the script

Running the program is simple. The first time you run it, you will be asked for your Spotify credientials which will be saved to a config file for ease of use in the future. Choose to sort results by hot or new, enter a post limit, and then enjoy.

```
python fresh.py
```

### Running the script using cron

We can use cron to automatically run the script periodically in order to keep it up-to-date. You will need either a macOS computer or Linux server to use cron.

1. Follow the `running the script` instructions to make sure your `.config.ini` file is generated with the required parameters
2. Run `crontab -e` to open the cron editor, which is similar to vim
3. Use the following format to create a line for your cron
    ```
    * * * * * command to be executed
    - - - - -
    | | | | |
    | | | | ----- Day of week (0 - 7) (Sunday=0 or 7)
    | | | ------- Month (1 - 12)
    | | --------- Day of month (1 - 31)
    | ----------- Hour (0 - 23)
    ------------- Minute (0 - 59)
    ```
    For example, you would do the following to run this everyday at 9AM
    ```
    0 9 * * * python /home/jsmith/fresh.py
    ```

## Contributing

I appreciate any help and support. Feel free to [fork](https://github.com/amcquade/fresh_script#fork-destination-box) and [create a pull request](https://github.com/amcquade/fresh_script/compare)
