# Quick reference to commmon shell tasks on Linux bash and Windows Powershell

## Network & Connectivity
### List of devices responding to ping (e.g.: 192.168.0.1-254)

    $ seq 1 254 | while read OCTET ; do IP="192.168.0.$OCTET" ;  \
    ( ping -W 1 -c 1 $IP > /dev/null && echo -en "\n" `date +"%F %T"` "\t$IP up." )   ; \
    done

    $ for OCTET in {1..254}  ; do IP="192.168.0.$OCTET" ;  \
    ( ping -W 1 -c 1 $IP > /dev/null && echo -en "\n" `date +"%F %T"` "\t$IP up." )   ; \
    done
   
    $ for OCTET in {1..254}  ; do IP="192.168.0.$OCTET" ;  \
    ( ( ping -W 1 -c 1 $IP > /dev/null && echo -en "\n" `date +"%F %T"` "\t$IP up." ) & ) ; \
    done ; echo "Completed."

EOF
