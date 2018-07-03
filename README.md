# REMOTE SHOP CONTROL
## PART
> **APPLICATION**
>> UI / UX DESIGN
>> BUSINESS LOGIC

> **DATABASE** <br>
> **WEB SERVER** <br>
> **RASP SERVER** <br>
> **DEVICE**

## ENVIRONMENTS
>|DIV|PART|PROGRAM|VER|
>|:-:|:-:|:-:|:-:|
>|WEB SERVER| OS | CentOS | 7 |
>|-|DB | MYSQL | 5.5|
>|-|Platform| NODE JS | 8.11.3 LTS |
>|-|Framework| EXPRESS | 4.16.3 |
>|DEVICE <br> ANDROID|  OS | android | - |
>|DEVICE <br> RASPBERRY | OS | - | - |

## REQUIREMENTS
> **REMOTE CONTROL**
>> User could check and control the state of the remote switch via application in own device.
>> **CONTROL** AND **CHECK**

## CONSTRAINTS
> **PERMISSION**
>>  The CONTROL function must be accessable to only authorized user.

## SCHEMA
### USER
>|FIELD|TYPE|NULL|KEY|DEFAULT|EXTRA|DESC|
>|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
>|ID|INT|N|PRI|NULL|AUTO_INCREMENT|USER ID
>|NAME|STRING|N||'NO NAME'||USER NAME
>|RDATE|DATE|N||CURRENT||REGISTER DATE

### REMOTE
>|FIELD|TYPE|NULL|KEY|DEFAULT|EXTRA|DESC|
>|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
>|ID|INT|N|PRI|NULL|AUTO_INCREMENT|REMOTE SWITCH ID
>|NAME|STRING|N||'NO NAME'||REMOTE NICK NAME
>|OWNER_ID|INT|N|FOREIGN|NULL||OWNER OF THE REMOTE DEVICE
>|RDATE|DATE|N||CURRENT||REGISTER DATE

## API DESC

>### SERVER
>#### RETURN object
> return : { code: number, data: retData , msg: 'message' } 
>>|FIELD|CODE|DESC|
>>|:-:|:-:|:-:|
>>|code|1|ok|
>>||2|server error|
>>||3|input error|
>>||4|database error|
>#### CONTROL ( '/control' )
>>|PATH|METHOD|PARAM|TYPE| DESC|
>>|:-:|:-:|:-:|:-:|:-:|
>>|'/on'|GET|owner ID|int|owner ID|
>>|-|-|device ID|int|device ID|
