
Example to enable BGP-LS in IOS-XR

Config example
```
router isis DEFAULT
 distribute bgp-ls                 
!
router bgp 11
 address-family link-state link-state
 !
 neighbor 172.16.17.2
  remote-as 11
  local address 172.16.17.101
  session-open-mode both
  address-family link-state link-state
  !
 !
!
```

Show output example:
```
RP/0/0/CPU0:XR1#show bgp all all
Sun Jun  7 12:24:14.862 UTC

Address Family: Link-state Link-state
------------------------------------

BGP router identifier 13.0.0.1, local AS number 11
BGP generic scan interval 60 secs
Non-stop routing is enabled
BGP table state: Active
Table ID: 0x0   RD version: 4626
BGP main routing table version 4626
BGP NSR Initial initsync version 1 (Reached)
BGP NSR/ISSU Sync-Group versions 0/0
BGP scan interval 60 secs

Status codes: s suppressed, d damped, h history, * valid, > best
              i - internal, r RIB-failure, S stale, N Nexthop-discard
Origin codes: i - IGP, e - EGP, ? - incomplete
Prefix codes: E link, V node, T IP reacheable route, u/U unknown
              I Identifier, N local node, R remote node, L link, P prefix
              L1/L2 ISIS level-1/level-2, O OSPF, D direct, S static
              a area-ID, l link-ID, t topology-ID, s ISO-ID,
              c confed-ID/ASN, b bgp-identifier, r router-ID,
              i if-address, n nbr-address, o OSPF Route-type, p IP-prefix
              d designated router address
   Network            Next Hop            Metric LocPrf Weight Path
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0010.0000.9999.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0101.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0103.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0104.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0105.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0106.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0002.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0003.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0004.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]]/328
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0010.0000.9999.02]]/336
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0101.02]]/336
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0101.03]]/336
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0102.02]]/336
                      0.0.0.0                                0 i
*> [V][L2][I0x0][N[c11][b13.0.0.1][s0110.0000.0102.03]]/336
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0010.0000.9999.00]][R[c11][b13.0.0.1][s0010.0000.9999.02]][L[i172.16.17.2]]/640
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]][R[c11][b13.0.0.1][s0130.0000.0002.00]][L[i13.1.2.0][n13.1.2.1]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]][R[c11][b13.0.0.1][s0130.0000.0005.00]][L[i13.1.5.0][n13.1.5.1]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]][R[c11][b13.0.0.1][s0010.0000.9999.02]]/576
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]][R[c11][b13.0.0.1][s0010.0000.9999.02]][L[i172.16.17.101][n172.16.17.2]]/704
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0002.00]][R[c11][b13.0.0.1][s0130.0000.0001.00]][L[i13.1.2.1][n13.1.2.0]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0002.00]][R[c11][b13.0.0.1][s0130.0000.0003.00]][L[i13.2.3.0][n13.2.3.1]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0002.00]][R[c11][b13.0.0.1][s0130.0000.0005.00]][L[i13.2.5.0][n13.2.5.1]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0003.00]][R[c11][b13.0.0.1][s0130.0000.0002.00]][L[i13.2.3.1][n13.2.3.0]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0003.00]][R[c11][b13.0.0.1][s0130.0000.0004.00]][L[i13.3.4.0][n13.3.4.1]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0003.00]][R[c11][b13.0.0.1][s0130.0000.0005.00]][L[i13.3.5.0][n13.3.5.1]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0004.00]][R[c11][b13.0.0.1][s0130.0000.0003.00]][L[i13.3.4.1][n13.3.4.0]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0004.00]][R[c11][b13.0.0.1][s0130.0000.0005.00]][L[i13.4.5.0][n13.4.5.1]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][R[c11][b13.0.0.1][s0130.0000.0001.00]][L[i13.1.5.1][n13.1.5.0]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][R[c11][b13.0.0.1][s0130.0000.0002.00]][L[i13.2.5.1][n13.2.5.0]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][R[c11][b13.0.0.1][s0130.0000.0003.00]][L[i13.3.5.1][n13.3.5.0]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][R[c11][b13.0.0.1][s0130.0000.0004.00]][L[i13.4.5.1][n13.4.5.0]]/696
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0010.0000.9999.02]][R[c11][b13.0.0.1][s0010.0000.9999.00]]/576
                      0.0.0.0                                0 i
*> [E][L2][I0x0][N[c11][b13.0.0.1][s0010.0000.9999.02]][R[c11][b13.0.0.1][s0130.0000.0001.00]]/576
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0010.0000.9999.00]][P[p172.16.17.0/24]]/392
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]][P[p172.16.17.0/24]]/392
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]][P[p13.1.2.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]][P[p13.1.5.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0001.00]][P[p13.0.0.1/32]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0002.00]][P[p13.1.2.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0002.00]][P[p13.2.3.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0002.00]][P[p13.2.5.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0002.00]][P[p13.0.0.2/32]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0003.00]][P[p13.2.3.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0003.00]][P[p13.3.4.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0003.00]][P[p13.3.5.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0003.00]][P[p13.0.0.3/32]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0004.00]][P[p13.3.4.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0004.00]][P[p13.4.5.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0004.00]][P[p13.0.0.4/32]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][P[p13.1.5.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][P[p13.2.5.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][P[p13.3.5.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][P[p13.4.5.0/31]]/400
                      0.0.0.0                                0 i
*> [T][L2][I0x0][N[c11][b13.0.0.1][s0130.0000.0005.00]][P[p13.0.0.5/32]]/400
                      0.0.0.0                                0 i

Processed 56 prefixes, 56 paths
RP/0/0/CPU0:XR1#
```


