# custom_commands
# To Create the custom command for your terminal follow the below steps

1. find the path of the in bulid command using "echo $PATH "
2. you will get some thing like this -> /var/labsstorage/home/manosundar4834/.vscode-server/bin/e4503b30fc78200f846c62cf8091b76ff5547662/bin/remote-cli:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
3. these are the location of command files , we are going to create a custom command in  any one this location 
4. let me take /usr/local/bin
5. open your terminal -> type the following command
6. cd /usr/local/bin
7. nano <file name>
8. type the code in nano editor
  

import requests
def get_random_quote():
	try:
		response = requests.get("https://quote-garden.herokuapp.com/api/v3/quotes/random")
		if response.status_code == 200:
			json_data = response.json()
			data = json_data['data']
	                print(data[0]['quoteText'])
		else:
			print("Error while getting quote")
	except:
		print("Something went wrong! Try Again!")
get_random_quote()
	
  
9. press ctr+q , Y and Enter 
10. In terminal type ls -l
    the newly created command is not executable , so inorder to excecute type ->
  sudo chmod +x <file name> or sudo chmod 667 <file name>
  #read-> +r , -r
  #write-> +w , -w
  #execute-> +x, -x
  while using the above one , it will be added and sub for all the parameters such as private, user , everyone
  but in  case of 667 , we can specify for particular parameter by considering alphabets as "1" and rest as "0"
  rw->110->6
  rw->110->6
  rwx->111->7
11. after making your command executable , it can be used in the terminal

  --manosundar manivel

  
