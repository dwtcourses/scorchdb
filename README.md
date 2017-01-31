# scorchdb
System configuration text files can be used to drive derived deployments and runbooks 

NAME

        scorchdb - light weight flat file text database

SYNOPSIS

        scorchdb [--file <filename>] [--list] [--full] [-<column name>]* <str> [+<column name> <str>] [-def "<col list>"]

OPTIONS

        --file <file>   Specify a file name to use

        --full          Ignore the columns and show the full line

        --list          List all available column names found in default
                        file or file specified
                        
        -def "<list>"   A space seperated list of column names to use. Useful when you want to
                        use the program on files that are not writable. i.e defining the /etc/passwd
                        file for scorchdb access ;
                          --file /etc/passwd -def "username shadow uid gid comment home shell"

        -<col> [-<col>] Display result for columns specified

        <regex string>  A regex expression used to return columns

        +<col> <string> Limit to next search string to the column mentioned (horizonal grep)
                        Although powerful this feature can be slow so only used when necessary.

EXAMPLES

        scorchdb host -ila

        Will display the columsn labelled l a and i from a file named host
        This might be the ip address, longname and alias to make a hosts file
