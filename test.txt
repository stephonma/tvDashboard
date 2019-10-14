set-ExecutionPolicy Unrestricted

$chromeArguments = '--start-fullscreen'

for (;;) {
  get-content "E:\My Downloads\urls.txt" | % {
    #start chrome.exe $_ ' --start-maximized'
    Start chrome.exe "$chromeArguments $_"
    Sleep 5 # pause
    Stop-Process -Name chrome 
  }
}