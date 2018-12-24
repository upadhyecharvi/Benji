'''
Authentication process and introduction to the chatbot
A dictionary would contain contacts and class room details of the faculty and can facilitate conversation
#conversation
Benji: Hello. Welcome to Benji. I am here to assist you with your technical requirements. What can I help you with today?
Faculty: Hello. I am <name>. I am conducting a class today in <room no.>.
Benji: okay. It says here that you will need a projector . what is it that you are teaching today?
Faculty: <something>
Benji. Okay. Do you need anything else with that?
Faculty: can you also add speaker to the list in <other room> ? We might need it .
Benji: Okay so speakers on 19th august 2018 in 205 tomorrow, is that right, <name>?
Faculty: Yes Thankyou Benji.
dirc1= {'room_no': 'N5_201', 'tech': ['speakers', 'projectors']}
dirc2= {'room_no': 'N5_204', 'tech':'projectors'}
dirc3= {'room_no': 'N5_208', 'tech':'T.V. Screeen'}
dirc4= {'room_no': 'N5_306', 'tech':'T.V.Screen'}
dirc5= {'room_no': 'N5_308', 'tech':'projectors'}
'''

dirc=dict()
dirc['N5_201']='projector'
dirc['N5_204']='[speakers,projector]'
dirc['N5_208']='T.V.Screen'
dirc['N5_306']='T.V.Screen'
dirc['N5_308']='projector'




print('Hello. Welcome to Benji. I am here to assist you with your technical requirements. What can I help you with today?') #explaination of what the chatbot actually does.
new_user= input('are you using this for the first time?(Y/N) :')
if new_user== 'yes' or 'YES' or 'Yes' or 'Y':
    username= input('create a new account: ')
    passw= input('new password: ')
    users=[]
    users.append(username)
    user_says=input('hi:')
elif new_user== 'no' or 'NO' or 'No' or 'N':
    old_username= input('enter username: ')
    if old_username in users :
        print('welcome! to Benji! what can i assist you with today?')
    else:
        print('please enter a valid username')
else:
    print('To use the Benji assistant in your classroom, please sign in.')
    new_user=input('new user?')

room_no=input('can you please enter the room number for your class?')
#user_says=input()
if room_no in dirc:
    print('okay. It says here that you will need a ',dirc[room_no],' what is it that you are teaching today?')
    user_reply=input('tell me your requirements: ')
elif 'i need help' in user_says:
    print('what exactly do you need my help for?')
    user_reply1=input('tell me your problem: ')
else:
    print('tell me your problem so that i can solve it.')
    user_reply1=input('Tell me your problem: ');

if 'setup' in user_reply :
    print('Every classroom is well equipped with the logistics. I will send someone for the setup.')
    user_reply2=input('Anything else: ')
elif 'projector' in user_reply :
    print('I will send someone immediately for the setup')
    user_reply2=input('Anything else: ')
elif 'speakers' in user_reply :
    print('I will send someone immediately for the setup')
    user_reply2=input('Anything else: ')
elif 'adapter' in user_reply :
    print('please send someone to collect the adapter from the tech dept')
    user_reply2=input('Anything else: ')
elif 'i dont understand anything' in user_reply:
    print('Hello, I am Benji, the tech and classroom assistant.')
    user_reply2= input('Anything else: ')
elif 'internet' in user_reply:
    print('If you are facing a problem with the internet, log out of the Cyber roam client and log in. Make sure you are connected to the Srishti N5 wifi.')
    user_reply2=input('Anything else: ')
elif 'help' in user_reply or 'presentation' in user_reply:
    print('I can help you set up and present your presentation. All you have to do is give commands')
    user_reply2=input('Anything else: ')
elif 'how does this work' in user_reply or 'can you do that' in user_reply or 'can you manage this' in user_reply:
    print('Hello, I am Benji, your classroom assistant and tech support. I can help you present content on your laptop or on the internet. I can keep a log of the devices you need and the list of requirements for your future classes and help you contact tech support.')
else:
    print('All the required devices can be collected from the tech team')
    user_reply2=input('Anything else:')


    if 'how does this work' in user_reply2 or 'can you do that' in user_reply2 or 'can you manage this' in user_reply2:
        print('Hello, I am Benji, your classroom assistant and tech support. I can help you present content on your laptop or on the internet. I can keep a log of the devices you need and the list of requirements for your future classes and help you contact tech support.')
        user_reply3=input()
    elif 'that is all'in user_reply2 or 'that is it' in user_reply2 or 'that would be all' in user_reply2 or 'thanks' in user_reply2 :
        print('So you are going to need ', dirc[room_no] , 'for your class. is that right?, ',username)
        user_reply3=input()

        if 'yes' in user_reply3 or 'right' in user_reply3 or 'Bingo' in user_reply3:
            print('thankyou for using this service. Have a nice day.')
