# Hello-world
the first repository
add one line


First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell

| Name | Description          |
| ------------- | ----------- |
| Help      | ~~Display the~~ help window.|
| Close     | _Closes_ a window     |


```shell
    # get all program status
    ${SCRIPT} <<EOF > ${DETAILS}
	  info all
	  exit
EOF

    # if any program's status isn't 'RUNNING', 
    # or there is no program, failed; otherwise, pass.
    awk ' 
        BEGIN {
            result = 255; # init result, means no program checked.
        }
        {
            if(NF == 5){
                if($2 == "RUNNING") {
                     result = 0
                } else {
                    exit 1; # check failed
                }
            }
        }
        END {
            exit result
        }
    ' ${DETAILS}
```
