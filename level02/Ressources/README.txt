ls -> level02.pcap

.pcap : pcap est une interface de programmation permettant de capturer un trafic réseau ("packet capture")

Use Wireshark (Set Up VM) or CloudShark (Web Based Service)

Wireshark > Export Packet Dissections > As plain text... &> file_name
grep "^00" file_name (Clean output on my mac : | cut -c 55- | tr -d '\n')

// cat data | xxd -r -p (-r : hex to ascii, -p : use plain format)

password = ft_wandr\x7f\x7f\x7fNDRel\x7fL0L => ft_waNDReL0L
