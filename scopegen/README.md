### About:
Generates **`.scope`** compatible format for TomNomNom's [Inscope](https://github.com/tomnomnom/hacks/tree/master/inscope)

### **Installation**
 - **Bash**: (Stable)
 ```bash
 sudo wget https://raw.githubusercontent.com/Azathothas/BugGPT-Tools/main/scopegen/scopegen.sh -O /usr/local/bin/scopegen.sh && sudo chmod +xwr /usr/local/bin/scopegen.sh
 ```
 - **Go**: (Stable & Preffered)
 ```bash
 go install -v github.com/Azathothas/BugGPT-Tools/scopegen@main
 ```
 - **Rust**: (Experimental)
 ```bash
 wget https://raw.githubusercontent.com/Azathothas/BugGPT-Tools/main/scopegen/scopegen.rs && rustc scopegen.rs && sudo mv scopegen $HOME/.cargo/bin
 ```
 ### Usage: `scopegen -h` will display help
 **Examples**: 
 `cat inscope-domains.txt`
```bash example.com
 example.org
 abc.example.com
 ```
 `cat outscope-domains.txt`
 ```bash
 oos.example.com
 oos.abc.example.org
 ```
 Then, **`scopegen -t inscope-domains.txt -in`** will generate **`inscope`**  domains:
 ```bash
 .*\.example\.com$
.*\.example\.org$
.*\.abc\.example\.com$
 ```
 similarly, **`scopegen -t outscope-domains.txt -os`** will generate **`outscope`**  domains:
 ```bash
!.*oos\.example\.com$
!.*oos\.abc\.example\.org$
 ```
 you can also pass **`stdin`**: 
```bash 
cat [inscope|outscope]-domains.txt | scopegen [-in | -os]
#or as echo
echo "example.com" | scopegen [-in | -os]
```


