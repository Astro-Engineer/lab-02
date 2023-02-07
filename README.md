# Lab 2
[Fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) this repo and clone it to your machine to get started!

## Team Members
- Michael Ruiz
- Isaiah Lee

## Lab Question Answers
#QC
Answer for Question 1: Any arguments given to function main(). Argument Count (argc) is an integer to the number of arguemnts given in terminal, while Argument Vector (argv) is an array of pointers to the arguments themselves.
Source: https://drive.google.com/drive/my-drive

Answer for Question 2: A UNIX file descriptor is an unsigned integer used to identify an open file. A file descriptor table gives the mapping between the descriptor and the data structure inside the kernel that represents the actual file connection.
https://www.usna.edu/Users/cs/wcbrown/courses/IC221/classes/L09/Class.html#:~:text=file%20descriptor%202%20is%20a,represents%20the%20actual%20file%20connection.

Answer for Question 3: Structs are a way to group several related variables into one place, where each variable is known as a member of the struct. sockaddr_in contains 2 members and includes 1 output function in case of error.

Answer for Question 4: The first input parameter is AF_INET, which is the address domain of the socket. The second paramter is SOCK_STREAM, which is the type of socket. The third parameter is the protocal, which should be 0, choosing the most appropriate protocal. The return value of socket() is an integer, which is the entry into the file descriptor table or a -1 if it fails.
https://www.linuxhowtos.org/C_C++/socket.htm

Answer for Question 5: For bind(), the arguments are:
1. sockfd, the return value from socket()
2. const struct sockaddr *addr, the address associated with the socket
3. socklen_t addrlen, the byte size of the address pointed to by addr
https://www.linuxhowtos.org/manpages/2/bind.htm
For listen(), the arguments are:
1. sockfd, same as before
2. int backlog, how big the backlog is that the socket can wait (0 on success, -1 on failure)
https://www.linuxhowtos.org/manpages/2/listen.htm

Answer for Question 6: The while loop ensures there is only 1 connection at a time. The code will not know which socket it is writing to if there are multiple connections.

Answer for Question 7: The function fork() creates a new process; the child process will close sockfd, allowing for another connection to be made.
https://www.linuxhowtos.org/C_C++/socket.htm

Answer for Question 8: A system call is a function that interacts with the operating system and is used to request actions that require special permissions. 
https://www.geeksforgeeks.org/introduction-of-system-call/

#QA 
Question 1: How did the reliability of UDP change when you added 50% loss to your local environment? Why did this occur?
The numbers would send but if the pace at which the numbers were sent was too fast the server would not be able to receive all of the numbers. The reliability suffered as a result. This is because packets are lost in UDP because it does not reqiure a connection.

Question 2: How did the reliability of TCP change? Why did this occur?
The reliability of TCP was not affected by the loss. This is due to retransmission of lost data packets.

Question 3: How did the speed of the TCP response change? Why might this happen?
The speed was heavily affected by the response change, and the numbers being sent would be registered much later compared to being sent without the 50% loss. This is because TCP guaruntees that all the data is sent and has multiple error checks, causing the process to slow down.

Sources:
https://www.lifesize.com/blog/tcp-vs-udp/#:~:text=TCP%20is%20a%20connection%2Doriented,is%20only%20possible%20with%20TCP. 


...
