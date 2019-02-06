# How to install Wordcloud CLI (Python) on Windows

Level: Basic

Just need to know how to enter URLs into web browsers and pressing `Windows`
keyboard button makes the Windows Start menu appear.

## Step 1
Enter this link into your web browser (e.g. Chrome):
<https://repo.anaconda.com/archive/Anaconda3-2018.12-Windows-x86_64.exe>

Download the file and save it anywhere in Windows.

(Optional) For extra info, the above link came from
<https://www.anaconda.com/distribution/>.

## Step 2
Run the downloaded file, which will install Anaconda. Simply press `Next >` and
`I Agree` in general, to make the installation proceed., without having to
change any default settings.

Wait for the installation to complete. This typically takes around 10-15
minutes.

When the green progress bar has disappeared, press `Skip`, and uncheck both
`Learn more about Anaconda Cloud` and `Learn how to get started with Anaconda`
boxes, and then press `Finish`.

## Step 3

Press the `Windows` button to make the Start menu appear, type `Anaconda Prompt`
and press `Enter` to run the prompt. You will be greeted with a black screen
with white text, which is known as simply the terminal.

## Step 4

Within the terminal, copy and paste the following (or type):

```bash
conda install -c https://conda.anaconda.org/conda-forge wordcloud
```

and press `ENTER` to run. Wait a while for the prompt `Proceed ([y]/n)?` to
appear. Type `y` and press `ENTER` to continue, and wait for a while to complete
the `wordcloud` installation.

(Optional) To ensure that the `wordcloud` program has been installed, type:
`wordcloud_cli --help` within the terminal. A bunch of usage text should appear
to indicate that you have installed correctly.

## Step 5

We will be running through a series of steps to understand how to use
`wordcloud_cli` program in an example scenario.

### Getting input text file and generating a simple output PNG image

Within the terminal, run the bunch of commands below.

You may enter line by line or just copy and paste the whole chunk and press
`ENTER`. For a start, you might encounter issue with trying to paste the text
copied from this guide, and the most consistent way to paste in the terminal
is to press this key combination:

`ALT+space` (together), then followed by `e`, then `p`.

Anyway moving on to the bunch of commands:

```bash
curl -s https://raw.githubusercontent.com/pogodevorg/awesome-pokemongo/master/README.md > input.txt
wordcloud_cli --text input.txt --imagefile output.png
output.png

```

The first line of command downloads a sample text file from some site and saves
into `input.txt`.

The second line of command runs `wordcloud_cli`, providing `input.txt` as the
text input, and generating a PNG output `output.png`.

The third and last line of command simply opens the `output.png` file for
preview.

By simply previewing the `output.png` PNG image file, we know that the sample
content has to do with Pokemon GO, based on the more impactful font size of the
wordings in the image.

In this step, we know that for a real usage scenario, we can simply replace
`input.txt` with your actual input text file to use. Note that the only
requirement is that this file contains text, and does not have to be saved as
a `.txt`. Other common text files include `.csv`, `.html`, `.xml`, etc.

### Restricting certain words or phrases from appearing

Still within the terminal, run the bunch of commands below:

```bash
python -c "print('\n'.join(['Pokemon','Go','PokemonGO','http','https','www','com','org','github','last','updated','aug','in','for','to','of','and','the','an','your']))" > stopwords.txt
wordcloud_cli --text input.txt --stopwords stopwords.txt --imagefile output.png
output.png

```

Here in first line of command, we have added stopwords (words that you want to
filter away and not show it on the image file).

In the second line of command, we have added the stopwords file into the running
of `wordcloud_cli`.

The third and last line of command is the same, to preview the `output.png`
file.

Now the image file are stripped away with the stopwords, and are filed with more
technical terms like `API`.

To see how the stopwords file look like, simply run:

```bash
stopwords.txt
```

Notice it is just a text file with a bunch of words, every word in a single
line. For a real usage scenario, simply open `Notepad` and save your own list
of words into a stopwords file.

### Adjusting the height and width of the output image

The default size of the image is likely to be too small. You can adjust the
output image file as follow by typing this:

```bash
wordcloud_cli --text input.txt --stopwords stopwords.txt --width 800 --height 600 --imagefile output.png
output.png

```

Now the image file would take longer to generate, but becomes much larger to our
delight.

Here, the first line of command now contains the width and height value. In real
usage scenario, simply change to the values that you desire.

### To know more about `wordcloud_cli`

Simply run:

```bash
wordcloud_cli --help
```

This gives you the bunch of parameters that you can use for the program,
including those we have come across from the series of steps done above.
