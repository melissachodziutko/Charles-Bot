

GUILD = "787398164667695184"


import discord
import random
import os

f = open("key.txt", "r+")
TOKEN = f.readline()
danny = f.readline()
me = f.readline()
client = discord.Client()


class writefile():
    f.write(TOKEN)
    f.write(danny)
    f.write(me)

def checkCommon(x):
    with open('people.txt', 'r') as f:
        myNames = [line.strip() for line in f]
    if x in myNames:
        if x == "<@!353710054878347264>":
            return "Danny"
        elif x == "<@!359859369157984256>":
            return "Melissa"
        else:
            return x.capitalize()
    elif x == 353710054878347264:
        return "Danny"
    elif x == 359859369157984256:
        return "Melissa"
    else:
        return "<" + x + ">"

def checkName(x):
    with open('people.txt', 'r') as f:
        myNames = [line.strip() for line in f]
    if x.lower() in myNames:
        if x.lower() == "danny":
            return "@!353710054878347264"
        elif x.lower() == "melissa":
            return "@!359859369157984256"
        else:
            return x
    else:
        return x

def responseSetup(x):
    y = x
    x = x.strip(">")
    x = x.strip("<")
    x = checkName(x)
    p = open(x + ".txt", "r+")
    nbp = p.readline()


@client.event
async def on_message(message):
    # we do not want the bot to reply to itself
    if message.author == client.user:
        return
    helloresponse = [" You're looking very sharp today!", " Don't miss training tonight.",
                     " You stayed up too late last night, I can tell.", " Good to see you so spry!"]
    goodmorning = ['good morning', 'good morning!']
    motivation = ['Success is not final, just as failure is not fatal. It is the courage to continue that counts.','Never be afraid of change, dear.','Every day is a day to make a positive change.','Once you realize your worth, then you can unlock your true potential.','Remember, the only thing that makes a hero is courage.']
    thanks = ["thanks charles","thank you, charles", "thanks, charles","thank you charles", "ty charles"]
    love = ['do you love me, charles?', 'do you love me, charles', 'do you love me charles','do you love me charles?']
    with open('people.txt', 'r') as f:
        myNames = [line.strip() for line in f]
    id = message.author.id
    print(id)
    print(message.content)
    if message.content.find("hey") and message.content.find("hi") and message.content.find("hello") and message.content.find("heww") != -1:
        msg2 = random.choice(helloresponse)
        msg = 'Hello {0.author.mention}'.format(message) + msg2.format(message)
        await message.channel.send(msg)
    if message.content.lower() in goodmorning:
        msg = 'Good morning {0.author.mention}!'.format(message)
        await message.channel.send(msg)
    if message.content.find("gm") != -1:
        msg = 'Good morning {0.author.mention}!'.format(message)
        await message.channel.send(msg)
    if message.content.lower() in thanks:
        msg = 'No problem, {0.author.mention}!'.format(message)
        await message.channel.send(msg)
    if message.content.lower() == "i need motivation":
        msg2 = random.choice(motivation)
        msg = 'Hey {0.author.mention}, '.format(message) + msg2.format(message)
        await message.channel.send(msg)
    if message.content.lower() in love:
        person = checkCommon(message.author.id)
        await message.channel.send("Of course I do, " + person)
    for x in myNames:
        if message.content == "naughty boy points " + x:
            y = x.strip(">" + "<")
            y = checkName(y)
            p = open(y + ".txt", "r+")
            nbp = p.readline()
            out = checkCommon(x)
            msg = out + " currently has "+ nbp + " points".format(message)
            await message.channel.send(msg)
        if message.content == "add naughty boy point " + x:
            y = x.strip(">" + "<")
            y = checkName(y)
            p = open(y + ".txt", "r+")
            nbp = p.readline()
            total = int(nbp) + 1
            po = open(y + ".txt", "w")
            po.write(str(total))
            po.close()
            out = checkCommon(x)
            msg = out + " currently has " + str(total) + " points now. Shame.".format(message)
            await message.channel.send(msg)


   # elif message.author.id == me:
        #if message.content.find("love me charles")!= -1:
           # msg = "You were always my favorite!"
            #await message.channel.send(msg)
    #elif message.author.id == danny:
        #if message.content.find("love me charles")!= -1:
            #msg = "Can't say I do..."
            #await message.channel.send(msg)





@client.event
async def on_ready():
    print('Logged in as')
    print(client.user.name)
    print(client.user.id)
    print('------')

client.run(TOKEN)
