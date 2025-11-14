```
awk 'BEGIN{ start="0" } { if($0 ~ /Log started: 2025-11-14/) { start="1"} if ( start == "1" && $0 ~ /Unpacking.*over/) {gsub(/[\s\t)( ]+/,"",$5); printf("%s=%s ", $2 , $5)}}' /var/log/apt/term.log
```
Then apt install the output

