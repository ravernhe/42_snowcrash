ls -> level02.pcap

# REFAIRE pour trainig Wireshark

.pcap : pcap est une interface de programmation permettant de capturer un trafic réseau ("packet capture")

Use Wireshark (Set Up VM) or CloudShark (Web Based Service)

tshark -Tfields -e data -r level02.pcap | tr -d '\n' > data

cat data | xxd -r -p (-r : hex to ascii, -p : use plain format)

password = ft_wandr\x7f\x7f\x7fNDRel\x7fL0L => ft_waNDReL0L