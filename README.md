# Peer-to-Peer-File-sharing-systems-Advanced-Operating-System-
Developed a Peer-2-Peer System for sharing the file over a network. Implemented User Interface for joining the network as well as searching the file among different systems. The user can decide to depart from the network and close all the connections. 

10 computers are connect to each other by P2P networks.
1) how the network is formed.
there is notepad file which maintains the record of computers in the network
say a computer wants to join the P2P network. It access this file and get the number of computers in the network stored in the file.
it does a random function and decides to join the network with any number of computers in the network
it sends a tcp connection request to each of the computers selected. The computers accept the request and add the name of this computer in their neighbor file.
the computer that sends the request adds the random nodes in it's neighbor file. Each computer  maintains it neighbor file.
If it is the first computer in the network it updates two files the neighbor file and the common file
2) how an element is searched.
each computer has set of files situated in the network. the search can be conducted in two ways both keyword and name of the file. There is main file something like an index file that contains a list of all the files in the network.
search request is sent to the computer  in the network. The computer searches in itself whether the file exists. If it is not there it in increases the hop count to 1 and starts a timer of 2 seconds, it also sends search request to the computers in the neighbor file and the computers once receiving a search request search in themselves if found return it, else send a  request to the their set of neighbor files and increase the hopcount. This search continues till the hop count reaches the number 16 or the timer completes the search for 2 seconds.
3) File transfer
   once the search is obtained the computer displays all the files in tuples along with their computer names
an overlay of networks is formed between two computers and file is transferred from the chosen computer to the searched computer.
4) Depart function-If a computer wants to depart from the network. It chooses a particular neighbor and sends all the information to that computer and sends that computers address to all other neighbors.
once sent the computer deletes its neighbor file and removes it's address from the the  network file.once received depart message,the other computers sends connect request to other given computer or computers.
Concurrent depart is also handled this way.

