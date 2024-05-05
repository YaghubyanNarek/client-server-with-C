# client-server-with-C
Created simple application with client and server side which is working with signals 


# Interprocess Communication using Signals in C

This is a simple demonstration of interprocess communication (IPC) between a client and a server using signals in C programming language. The client sends text to the server by encoding each character into 8 bits and sending these bits as signals to the server process, where they are decoded and printed.

## Project Structure

- `server.c`: Contains the server code that listens for signals from the client, decodes the received bits, and prints the corresponding characters.
- `client.c`: Contains the client code that takes input text from the user, encodes it into bits, and sends the bits to the server process.
- `README.md`: This file, providing an overview of the project.
- `Makefile`: A Makefile for compiling the server and client programs.

## How to Use

1. Compile the server and client programs using the provided Makefile.
    ```bash
    make
    ```

2. Run the server program in one terminal window.
    ```bash
    ./server
    ```

3. Note the process ID (PID) of the server.

4. Run the client program in another terminal window, providing the server's PID as an argument.
    ```bash
    ./client <server_pid>
    ```

5. Type the text you want to send to the server in the client terminal window and press Enter. The text will be displayed in the server terminal window after being received and decoded.

6. Repeat step 5 as needed to send more text.

7. To exit, press `Ctrl + C` in both the server and client terminal windows.

## Notes

- The communication between the client and server is achieved using signals `SIGUSR1` and `SIGUSR2`. `SIGUSR1` represents a binary `1`, and `SIGUSR2` represents a binary `0`.
- The server decodes the received bits into characters and prints them to the console.
- The client encodes each character of the input text into 8 bits and sends these bits to the server.
- The communication is one-way, from the client to the server.

Feel free to modify and extend this code for your specific use case or learning purposes!
