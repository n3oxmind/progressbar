# progressbar
progressbar is a simple bash progress bar that can be used directly from the command-line or from inside a shell script. It also supports printf string format to be added before the progress bar by using the [printf string format] operator. 

### progressbar.sh can display the progress bar in two different format
1. inline progress bar  
output text: [#############] ET: 3.00s
2. Display the progress bar on a separate line  
Output text:  
[#############] ET: 3.00s

### Using progressbar.sh from the command-line
#### simple progressbar on a separate line 
```sh
$ ./progressbar.sh "sleep 3"
[#############] ET: 3.00s
```
#### progressbar with simple text 
```sh
$ ./progressbar.sh "sleep 3" "Output"
Output: [#############] ET: 3.00s
```
#### progressbar with formated text (printf format)
```sh
$ ./progressbar .sh "sleep 3" "[%-20s]Output"   # printf left alignment by 20
Output              [#############] ET: 3.00s
```
```sh
$ ./progressbar .sh "sleep 3" "[\t%15s]Output"   # printf tab and right alignment 
	         Output[#############] ET: 3.00s
```
You can add and printf string format between square brackets `[]` as a 2nd argument.

### Using progressbar.sh from inside your script
1. Add progressbar.sh to your script directory and make it executable.  
$ chmod +x progressbar.sh
2. Add this line to your script   
source ~/path/to/progressbar.sh
3. call `progress_bar` function see examples bellow:  
progress_bar "myfunction"  
progress_bar "myfunction" "[%-20s]sometext"  
progress_bar "myfunction" "[\t%20s]sometext"  
