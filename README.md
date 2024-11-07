!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname R1
!
!
!
enable secret 5 $1$mERr$hx5rVt7rPNoS4wqbXKX7m0
!
!
!
ip dhcp pool vlan30
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
 dns-server 8.8.8.8
ip dhcp pool vlan20
 network 192.168.20.0 255.255.255.0
 default-router 192.168.20.1
 dns-server 8.8.8.8
!
!
!
ip cef
no ipv6 cef
!
!
!
username admin password 0 1234
!
!
license udi pid CISCO2911/K9 sn FTX15247F47-
!
!
!
!
!
!
!
!
!
ip domain-name wmszki.hu
!
!
spanning-tree mode pvst
!
!
!
!
!
!
interface GigabitEthernet0/0
 no ip address
 duplex auto
 speed auto
!
interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 192.168.10.1 255.255.255.0
!
interface GigabitEthernet0/1
 ip address 172.20.25.1 255.255.255.252
 duplex auto
 speed auto
!
interface GigabitEthernet0/2
 no ip address
 duplex auto
 speed auto
!
interface GigabitEthernet0/2.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
!
interface Vlan1
 no ip address
 shutdown
!
ip classless
!
ip flow-export version 9
!
!
!
!
!
!
!
line con 0
!
line aux 0
!
line vty 0 4
 password 1234
 login local
 transport input ssh
line vty 5 15
 password 1234
 login local
 transport input ssh
!
!
!
end
