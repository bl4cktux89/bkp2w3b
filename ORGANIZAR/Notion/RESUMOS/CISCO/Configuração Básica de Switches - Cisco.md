## Hostname

```Plain
Switch# configure terminal
Switch(config)# hostname Sw-Floor-1
Sw-Floor-1(config)#
```

## Senha

```Plain
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line console 0
Sw-Floor-1(config-line)# password cisco
Sw-Floor-1(config-line)# login
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

```Plain
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# enable secret class
Sw-Floor-1(config)# exit
Sw-Floor-1#
```

```Plain
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# 1(config)# line vty 0 15
Sw-Floor-1(config-line)# password cisco 
Sw-Floor-1(config-line)# login 
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

## Criptografar Senhas

```Plain
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# service password-encryption
Sw-Floor-1(config)#
```

```Plain
1(config)# endSw-Floor-
Sw-Floor-1# show running-config
!

!
line con 0
password 7 094F471A1A0A 
login
!
line vty 0 4
password 7 03095A0F034F38435B49150A1819
login
!
!
end
```

## Mensagens de Banner

```Plain
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# banner motd \#a mensagem do dia#
```