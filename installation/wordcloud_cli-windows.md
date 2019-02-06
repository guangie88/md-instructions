# How to install Wordcloud CLI (Python) on Windows

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

TODO
