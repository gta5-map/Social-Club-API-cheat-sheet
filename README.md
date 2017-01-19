# Rockstar / R* Social Club "API" cheat sheet

In the guide below, you can find some useful information how to obtain public statistics of Social Club profiles, Rockstar's official platform for GTA Online statistics. Either how many times you blew up a police helicopter or how often you died through a jerry can – it's all tracked and viewable online on said platform. 

Unfortunately, it's only made for humans to look at in the browser and if people want to build a script to parse the information, it is rather tricky to access and parse the desired piece of information using cURL since the website is using lots of JavaScript and AJAX to reload stuff in the background. 

In [this guide](http://rockstar-api.rtfd.io) I will try to describe and collect as many useful knowledge about the Social Club and it's "API" as possible.

**Disclaimer**: Using this guide might be a violation of Rockstar's [Terms of Service](http://www.rockstargames.com/legal). I take no responsibility for the way you use it. Any violation of the [TOS](http://www.rockstargames.com/legal) resulting from using this cheat sheet is entirely the user's responsibility.

## Installation

1. Clone this repository:

    ```
    git clone https://github.com/gta5-map/Social-Club-API-cheat-sheet
    cd Social-Club-API-cheat-sheet
    ```

2. Make sure you've installed all requirements:

    ```
    pip install -r requirements.txt
    ```

3. Build the docs/HTML using `make`:
    
    ```
    make clean html
    ```

4. Open the built HTML using your browser:

    ```
    open docs/_build/html/index.html
    ```

## Contributing

1. Fork it
2. Create your feature branch: `git checkout -b feature/my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin feature/my-new-feature`
5. Submit a pull request

## Requirements / Dependencies

* Python
* Sphinx

## Version

1.1.0

## License

[MIT](LICENSE)
