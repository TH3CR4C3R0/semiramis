#!/usr/bin/python3
# Created by TH3CR4C3R0

import requests
import colorama
from colorama import Fore, Style

#/usr/share/dirb/wordlists/common.txt
try:
    url = input(Fore.BLUE + 'url > ')
    name = input(Fore.BLUE+'file path > ')
    file = open(name , 'r')
    read = file.read()
    readp = read.splitlines()
    print(Fore.YELLOW + str(len(readp)) + ' Words')

    for x in range(158 , len(readp)):
        if requests.get(url + '/' + readp[x]).status_code == 200:
            print(Fore.RED + '[*][Found] ' + url + str('/' +readp[x])+ '       [' + str(requests.get(url + '/' + readp[x]).status_code) +']')
        elif requests.get(url + '/' + readp[x]).status_code == 403:
            print(Fore.YELLOW + '[!][Forbidden] ' + url + str('/' +readp[x]))
        else:
            print(Fore.GREEN + 'Try ['+str(x)+'] Not a dir > ' + str(url + '/' +readp[x]))

except KeyboardInterrupt :
    print(Fore.YELLOW + '\nProccess Interrupt')
except requests.exceptions.MissingSchema:
    print(Fore.YELLOW + '\nMake sure that http:// or https:// are before the web address\nAlso make sure that it is valid address')
except FileNotFoundError :
    print(Fore.YELLOW + 'File path is not valid\nMake sure that the file path is witten in the right syntax')
except UnicodeDecodeError:
    print('Unicode decode error > file must be decoded first')
