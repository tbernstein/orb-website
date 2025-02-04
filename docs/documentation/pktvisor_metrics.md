# Orb Metrics

The Orb metrics currently provided come from the various supported pktvisor handlers and are listed here by handler.<br>
For handlers that have metric groups, the metric groups that must be enabled for the metric to exist are listed in "Metric Groups" column. `any group*` means that the metric will exist for any valid metric groups that is enabled.


## DHCP Metrics
<font size="1">[Check how to activate dhcp metrics](/documentation/advanced_policies/#dhcp-analyzer-dhcp)</font>

| Metric                                                                                   | Prometheus Name                    |
|------------------------------------------------------------------------------------------|------------------------------------|
| Quantiles of all DHCP wire packets (combined ingress and egress) in packets per second   | dhcp\_rates\_total                 |
| Total sum of all DHCP wire packets (combined ingress and egress) in packets per second   | dhcp\_rates\_total\_sum            |
| Count of all DHCP wire packets (combined ingress and egress) in packets per second       | dhcp\_rates\_total\_count          |
| Quantiles of all DHCP wire packets before filtering per second                           | dhcp\_rates\_events                |
| Total sum of all DHCP wire packets before filtering per second                           | dhcp\_rates\_events\_sum           |
| Count of all DHCP wire packets before filtering per second                               | dhcp\_rates\_events\_count         |
| Top DHCP servers                                                                         | dhcp\_top\_servers                 |
| Top DHCP clients                                                                         | dhcp\_top\_clients                 |
| Total DHCP packets with message type ACK                                                 | dhcp\_wire\_packets\_ack           |
| Total DHCPv6 packets with message type ADVERTISE                                         | dhcp\_wire\_packets\_advertise     |
| Total DHCP wire packets that were sampled for deep inspection                            | dhcp\_wire\_packets\_deep\_samples |
| Total DHCP packets with message type DISCOVER                                            | dhcp\_wire\_packets\_discover      |
| Total DHCP wire packets events                                                           | dhcp\_wire\_packets\_events        |
| Total DHCP/DHCPv6 wire packets seen that did not match the configured filter(s) (if any) | dhcp\_wire\_packets\_filtered      |
| Total DHCP packets with message type OFFER                                               | dhcp\_wire\_packets\_offer         |
| Total DHCPv6 packets with message type REPLY                                             | dhcp\_wire\_packets\_reply         |
| Total DHCP packets with message type REQUEST                                             | dhcp\_wire\_packets\_request       |
| Total DHCPv6 packets with message type REQUEST                                           | dhcp\_wire\_packets\_request_v6    |
| Total DHCPv6 packets with message type SOLICIT                                           | dhcp\_wire\_packets\_solicit       |
| DORA packet counts                                                                       | dhcp\_wire\_packets\_total         |

## DNS Metrics
<font size="1">[Check how to activate/deactivate dns metrics](/documentation/advanced_policies/#dns-analyzer-dns)</font>


=== "v1"
    
    | Metric                                                                                       | Prometheus Name                      | Metric Groups                   |
    |----------------------------------------------------------------------------------------------|--------------------------------------|---------------------------------|
    | Cardinality of unique QNAMES, both ingress and egress                                        | dns\_cardinality\_qname              | cardinality                     |
    | Quantiles of rates for DNS packets processed by policy                                       | dns\_rates\_total                    | any group*                      |
    | Total sum of rates for DNS packets processed by policy                                       | dns\_rates\_total\_sum               | any group*                      |
    | Count of rates for DNS packets processed by policy                                           | dns\_rates\_total\_count             | any group*                      |
    | Quantiles of all DNS wire packets before filtering per second                                | dns\_rates\_events                   | any group*                      |
    | Total sum of all DNS wire packets before filtering per second                                | dns\_rates\_events\_sum              | any group*                      |
    | Count of all DNS wire packets before filtering per second                                    | dns\_rates\_events\_count            | any group*                      |
    | Top ECS ASNs                                                                                 | dns\_top\_asn\_ecs                   | top_ecs                         |
    | Top ECS GeoIP locations                                                                      | dns\_top\_geoLoc\_ecs                | top_ecs                         |
    | Top QNAMES with response code NOERROR and no data in the response (NODATA)                   | dns\_top\_nodata                     | top_qnames                      |
    | Top QNAMES with response code NXDOMAIN                                                       | dns\_top\_nxdomain                   | top_qnames                      |
    | Top QNAMES by response volume                                                                | dns\_top\_qname\_by\_resp\_bytes     | top_qnames_details + top_qnames |
    | Top QNAMES with result code NOERROR                                                          | dns\_top\_noerror                    | top_qname_details + top_qnames  |
    | Top QNAMES aggregated at a depth of two labels                                               | dns\_top\_qname2                     | top_qnames                      |
    | Top QNAMES aggregated at a depth of three labels                                             | dns\_top\_qname3                     | top_qnames                      |
    | Top QTYPEs                                                                                   | dns\_top\_qtype                      | any group*                      |
    | Top EDNS Client Subnets (ECS)                                                                | dns\_top\_query\_ecs                 | top_ecs                         |
    | Top RCODEs                                                                                   | dns\_top\_rcode                      | any group*                      |
    | Top QNAMES with response code REFUSED                                                        | dns\_top\_refused                    | top_qnames                      |
    | Top QNAMES with response code SRVFAIL                                                        | dns\_top\_srvfail                    | top_qnames                      |
    | Top UDP source ports of DNS queries                                                          | dns\_top\_udp\_ports                 | top_ports                       |
    | Total DNS wire packets sampled for deep inspection                                           | dns\_wire\_packets\_deep\_samples    | any group*                      |
    | Count of DNS packets sent to policy                                                          | dns\_wire\_packets\_events           | any group*                      |
    | Count of DNS packets filtered out by policy                                                  | dns\_wire\_packets\_filtered         | counters                        |
    | Count of DNS packets received over IPv4                                                      | dns\_wire\_packets\_ipv4             | counters                        |
    | Count of DNS packets received over IPv6                                                      | dns\_wire\_packets\_ipv6             | counters                        |
    | Count of DNS packets flagged as reply and identified as NODATA                               | dns\_wire\_packets\_nodata           | counters                        |
    | Count of DNS packets flagged as reply with response code NOERROR                             | dns\_wire\_packets\_noerror          | counters                        |
    | Count of DNS packets flagged as reply with response code NXDOMAIN                            | dns\_wire\_packets\_nxdomain         | counters                        |
    | Count of DNS packets flagged as query                                                        | dns\_wire\_packets\_queries          | counters                        |
    | Count of DNS packets with EDNS Client Subnet (ECS) option set                                | dns\_wire\_packets\_query\_ecs       | counters + top_ecs              |
    | Count of DNS packets flagged as reply with response code REFUSED                             | dns\_wire\_packets\_refused          | counters                        |
    | Count of DNS packets flagged as reply                                                        | dns\_wire\_packets\_replies          | counters                        |
    | Count of DNS packets flagged as reply with response code SRVFAIL                             | dns\_wire\_packets\_srvfail          | counters                        |
    | Count of DNS packets received over TCP                                                       | dns\_wire\_packets\_tcp              | counters                        |
    | Count of DNS packets matched by policy                                                       | dns\_wire\_packets\_total            | counters                        |
    | Count of DNS packets received over UDP                                                       | dns\_wire\_packets\_udp              | counters                        |
    | Total DNS wire packets received over DNS over HTTPS                                          | dns\_wire\_packets\_doh              | counters (dnstap)               |
    | Total DNS wire packets received over DNS over TLS                                            | dns\_wire\_packets\_dot              | counters (dnstap)               |
    | Total number of DNS transactions that timed out                                              | dns\_xact\_counts\_timed\_out        | dns_transaction                 |
    | Total DNS transactions (query/reply pairs)                                                   | dns\_xact\_counts\_total             | dns_transaction                 |
    | Quantiles of transaction timing (query/reply pairs) when host is server, in microseconds     | dns\_xact\_in\_quantiles\_us         | dns_transaction                 |
    | Total sum of transaction timing (query/reply pairs) when host is server, in microseconds     | dns\_xact\_in\_quantiles\_us\_sum    | dns_transaction                 |
    | Count of transaction timing (query/reply pairs) when host is server, in microseconds         | dns\_xact\_in\_quantiles\_us\_count  | dns_transaction                 |
    | Top QNAMES in transactions where host is the server and transaction speed is slower than p90 | dns\_xact\_in\_top\_slow             | dns_transaction                 |
    | Total ingress DNS transactions (host is server)                                              | dns\_xact\_in\_total                 | dns_transaction                 |
    | Quantiles of transaction timing (query/reply pairs) when host is client, in microseconds     | dns\_xact\_out\_quantiles\_us        | dns_transaction                 |
    | Total sum of transaction timing (query/reply pairs) when host is client, in microseconds     | dns\_xact\_out\_quantiles\_us\_sum   | dns_transaction                 |
    | Count of transaction timing (query/reply pairs) when host is client, in microseconds         | dns\_xact\_out\_quantiles\_us\_count | dns_transaction                 |
    | Top QNAMES in transactions where host is the client and transaction speed is slower than p90 | dns\_xact\_out\_top\_slow            | dns_transaction                 |
    | Total egress DNS transactions (host is client)                                               | dns\_xact\_out\_total                | dns_transaction                 |
    | Distribution of response/query size ratios                                                   | dns\_xact\_ratio\_quantiles          | dns_transaction                 |
    | Total sum of response/query size ratios                                                      | dns\_xact\_ratio\_quantiles\_sum     | dns_transaction                 |
    | Count of response/query size ratios                                                          | dns\_xact\_ratio\_quantiles\_count   | dns_transaction                 |


=== "v2"

    !!! warning
    
        Status: `Beta`. The metric names and configuration options may still change
    
    | Metric                                                                                                                 | Prometheus Name                     | Metric Groups |
    |------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
    | Quantiles of all DNS wire packets before filtering per second	                                                         | dns_rates_observed_pps              | any group*    |
    | Count of all DNS wire packets before filtering per second		                                                         | dns_rates_observed_pps_count        | any group*    |
    | Total sum of rates for DNS packets processed by policy	                                                             | dns_rates_observed_pps_sum          | any group*    |
    | Total DNS transactions (query/reply pairs) with the AD flag set in the response                                        | dns_authenticated_data_xacts        | counters      |
    | Total DNS transactions (query/reply pairs) with the AA flag set in the response                                        | dns_authoritative_answer_xacts      | counters      |
    | Cardinality of unique QNAMES, both ingress and egress	                                                                 | dns_cardinality_qname               | cardinality   |
    | Total DNS transactions (query/reply pairs) with the CD flag set in the query                                           | dns_checking_disabled_xacts         | counters      |
    | Total DNS wire packets that were sampled for deep inspection                                                           | dns_deep_sampled_packets            | any group*    |
    | Total DNS transactions (query/reply pairs) received over DNSCrypt over TCP                                             | dns_dnscrypt_tcp_xacts              | counters      |
    | Total DNS transactions (query/reply pairs) received over DNSCrypt over UDP                                             | dns_dnscrypt_udp_xacts              | counters      |
    | Total DNS transactions (query/reply pairs) received over DNS over HTTPS                                                | dns_doh_xacts                       | counters      |
    | Total DNS transactions (query/reply pairs) received over DNS over QUIC                                                 | dns_doq_xacts                       | counters      |
    | Total DNS transactions (query/reply pairs) received over DNS over TLS                                                  | dns_dot_xacts                       | counters      |
    | Total DNS transactions (query/reply pairs) with the EDNS Client Subnet option set                                      | dns_ecs_xacts                       | counters      |
    | Total DNS wire packets seen that did not match the configured filter(s) (if any)                                       | dns_filtered_packets                | counters      |
    | Total DNS transactions (query/reply pairs) received over IPv4                                                          | dns_ipv4_xacts                      | counters      |
    | Total DNS transactions (query/reply pairs) received over IPv6                                                          | dns_ipv6_xacts                      | counters      |
    | Total DNS transactions (query/reply pairs) flagged as reply with return code NOERROR but with an empty answers section | dns_nodata_xacts                    | counters      |
    | Total DNS transactions (query/reply pairs) flagged as reply with return code NOERROR                                   | dns_noerror_xacts                   | counters      |
    | Total DNS transactions (query/reply pairs) flagged as reply with return code NXDOMAIN                                  | dns_nxdomain_xacts                  | counters      |
    | Total DNS wire packets events                                                                                          | dns_observed_packets                | any group*    |
    | Total number of DNS responses that do not have a corresponding query                                                   | dns_orphan_responses                | counters      |
    | Total DNS transactions (query/reply pairs) flagged as reply with return code REFUSED                                   | dns_refused_xacts                   | counters      |
    | Quantiles of ratio of packet sizes in a DNS transaction (reply/query)                                                  | dns_response_query_size_ratio       | top_size      |
    | Count of ratio of packet sizes in a DNS transaction (reply/query)                                                      | dns_response_query_size_ratio_count | top_size      |
    | Total sum of ratio of packet sizes in a DNS transaction (reply/query)                                                  | dns_response_query_size_ratio_sum   | top_size      |
    | Total DNS transactions (query/reply pairs) flagged as reply with return code SRVFAIL                                   | dns_srvfail_xacts                   | counters      |
    | Total DNS transactions (query/reply pairs) received over TCP                                                           | dns_tcp_xacts                       | counters      |
    | Total number of DNS queries that timed out                                                                             | dns_timeout_queries                 | counters      |
    | Top ASNs by ECS                                                                                                        | dns_top_asn_ecs_xacts               | top_ecs       |
    | Top EDNS Client Subnet (ECS) observed in DNS transaction                                                               | dns_top_ecs_xacts                   | top_ecs       |
    | 	     Top GeoIP ECS locations                                                                                          | dns_top_geo_loc_ecs_xacts           | top_ecs       |
    | 	  Top QNAMES with result code NOERROR and empty answer section                                                        | dns_top_nodata_xacts                | top_rcodes    |
    | Top QNAMES with result code NOERROR                                                                                    | dns_top_noerror_xacts               | top_rcodes    |
    | 	    Top QNAMES with result code NXDOMAIN                                                                              | dns_top_nxdomain_xacts              | top_rcodes    |
    | 	      Top QNAMES, aggregated at a depth of two labels                                                                 | dns_top_qname2_xacts                | top_qnames    |
    | Top QNAMES, aggregated at a depth of three labels                                                                      | dns_top_qname3_xacts                | top_qnames    |
    | Top QNAMES by response volume in bytes                                                                                 | dns_top_response_bytes              | top_size      |
    | Top query types                                                                                                        | dns_top_qtype_xacts                 | top_qtypes    |
    | 	    Top result codes                                                                                                  | dns_top_rcode_xacts                 | top_rcodes    |
    | 	         Top QNAMES with result code REFUSED                                                                          | dns_top_refused_xacts               | top_rcodes    |
    | Top QNAMES in transactions where host is the server and transaction speed is slower than p90                           | dns_top_slow_xacts                  | xact_times    |
    | 	    Top QNAMES with result code SRVFAIL                                                                               | dns_top_srvfail_xacts               | top_rcodes    |
    | 	     Top UDP source port on the query side of a transaction                                                           | dns_top_udp_ports_xacts             | top_ports     |
    | Total DNS transactions (query/reply pairs) received over UDP                                                           | dns_udp_xacts                       | counters      |
    | Rate of all DNS transaction (reply/query) per second                                                                   | dns_xact_rates                      | quantiles     |
    | Count of all DNS transaction (reply/query) per second                                                                  | dns_xact_rates_count                | quantiles     |
    | Total sum of all DNS transaction (reply/query) per second                                                              | dns_xact_rates_sum                  | quantiles     |
    | Quantiles of transaction timing (query/reply pairs) in microseconds                                                    | dns_xact_time_us                    | xact_times    |
    | Count of transaction timing (query/reply pairs) in microseconds                                                        | dns_xact_time_us_count              | xact_times    |
    | Total sum of transaction timing (query/reply pairs) in microseconds                                                    | dns_xact_time_us_sum                | xact_times    |
    | Total DNS transactions (query/reply pairs)                                                                             | dns_xacts                           | counters      |



## Network Metrics
<font size="1">[Check how to activate/deactivate network metrics](/documentation/advanced_policies/#network-l2-l3-analyzer-net)</font>

=== "v1"
    
    | Metric                                                          | Prometheus Name                     | Metric Groups |
    |-----------------------------------------------------------------|-------------------------------------|---------------|
    | Destination IP cardinality                                      | packets\_cardinality\_dst\_ips\_out | cardinality   |
    | Source IP cardinality                                           | packets\_cardinality\_src\_ips\_in  | cardinality   |
    | Count of packets sampled for deep inspection                    | packets\_deep\_samples              | any group*    |
    | Count of packets sent to policy                                 | packets\_events                     | any group*    |
    | Count of packets filtered out by policy                         | packets\_filtered                   | counters      |
    | Count of ingress packets                                        | packets\_in                         | counters      |
    | Count of IPv4 packets                                           | packets\_ipv4                       | counters      |
    | Count of IPv6 packets                                           | packets\_ipv6                       | counters      |
    | Count of packets not UDP or TCP                                 | packets\_other\_l4                  | counters      |
    | Count of egress packets                                         | packets\_out                        | counters      |
    | Quantiles of packet payload sizes                               | packets\_payload\_size              | any group*    |
    | Total sum of packet payload sizes                               | packets\_payload\_size\_sum         | any group*    |
    | Count of packet payload sizes                                   | packets\_payload\_size\_count       | any group*    |
    | Count of TCP packets with SYN flag set                          | packets\_protocol\_tcp\_syn         | counters      |
    | Quantiles of ingress data rates                                 | payload\_rates\_bytes\_in           | any group*    |
    | Total sum of ingress data rates                                 | payload\_rates\_bytes\_in\_sum      | any group*    |
    | Count of ingress data rates                                     | payload\_rates\_bytes\_in\_count    | any group*    |
    | Quantiles of egress data rates                                  | payload\_rates\_bytes\_out          | any group*    |
    | Total sum of egress data rates                                  | payload\_rates\_bytes\_out\_sum     | any group*    |
    | Count of egress data rates                                      | payload\_rates\_bytes\_out\_count   | any group*    |
    | Quantiles of total data rates                                   | payload\_rates\_bytes\_total        | any group*    |
    | Total sum of total data rates                                   | payload\_rates\_bytes\_total\_sum   | any group*    |
    | Count of total data rates                                       | payload\_rates\_bytes\_total\_count | any group*    |
    | Quantiles of all packets before filtering in packets per second | payload\_rates\_pps\_events         | any group*    |
    | Total sum of all packets before filtering in packets per second | payload\_rates\_pps\_events\_sum    | any group*    |
    | Count of all packets before filtering in packets per second     | payload\_rates\_pps\_events\_count  | any group*    |
    | Quantiles of ingress packet rates                               | payload\_rates\_pps\_in             | any group*    |
    | Total sum of ingress packet rates                               | payload\_rates\_pps\_in\_sum        | any group*    |
    | Count of ingress packet rates                                   | payload\_rates\_pps\_in\_count      | any group*    |
    | Quantiles of egress packet rates                                | payload\_rates\_pps\_out            | any group*    |
    | Total sum of egress packet rates                                | payload\_rates\_pps\_out\_sum       | any group*    |
    | Count of egress packet rates                                    | payload\_rates\_pps\_out\_count     | any group*    |
    | Quantiles of total packet rates                                 | payload\_rates\_pps\_total          | any group*    |
    | Total sum of total packet rates                                 | payload\_rates\_pps\_total\_sum     | any group*    |
    | Count of total packet rates                                     | payload\_rates\_pps\_total\_count   | any group*    |
    | Count of TCP packets                                            | packets\_tcp                        | counters      |
    | Top ASNs                                                        | packets\_top\_ASN                   | top_geo       |
    | Top GeoIP locations                                             | packets\_top\_geoLoc                | top_geo       |
    | Top IPv4 IP addresses                                           | packets\_top\_ipv4                  | top_ips       |
    | Top IPv6 IP addresses                                           | packets\_top\_ipv6                  | top_ips       |
    | Count of packets matched by policy                              | packets\_total                      | counters      |
    | Count of UDP packets                                            | packets\_udp                        | counters      |
    | Count of packets of unknown direction                           | packets\_unknown\_dir               | counters      |

=== "v2"

    !!! warning
    
        Status: `Beta`. The metric names and configuration options may still change
    
    | Metric                                                                  | Prometheus Name              | Metric Groups |
    |-------------------------------------------------------------------------|------------------------------|---------------|
    | IP cardinality                                                          | net_cardinality_ips          | cardinality   |         
     | Total packets that were sampled for deep inspection                     | net_deep_sampled_packets     | any group*    |    
     | Total packets seen that did not match the configured filter(s) (if any) | net_filtered_packets         | counters      |        
     | Count of IPv4 packets                                                   | net_ipv4_packets             | counters      |            
     | Count of IPv6 packets                                                   | net_ipv6_packets             | counters      |            
     | Total packets events generated                                          | net_observed_packets         | any group*    |        
     | Count of packets which are not UDP or TCP                               | net_other_l4_packets         | counters      |        
     | Quantiles of payload sizes, in bytes                                    | net_payload_size_bytes       | quantiles     |      
     | Count of payload sizes, in bytes                                        | net_payload_size_bytes_count | quantiles     |
     | Total sum of payload sizes, in bytes                                    | net_payload_size_bytes_sum   | quantiles     |  
     | Data rate of bits per second                                            | net_rates_bps                | quantiles     |               
     | Count of bits per second                                                | net_rates_bps_count          | quantiles     |         
     | Total sum of bits per second                                            | net_rates_bps_sum            | quantiles     |           
     | Rate of all packets before filtering per second                         | net_rates_observed_pps       | any group*    |      
     | Count of all packets before filtering per second                        | net_rates_observed_pps_count | any group*    |
     | Total sum of all packets before filtering per second                    | net_rates_observed_pps_sum   | any group*    |  
     | Rate of packets per second                                              | net_rates_pps                | quantiles     |               
     | Count of packets per second                                             | net_rates_pps_count          | quantiles     |         
     | Total sum of packets per second                                         | net_rates_pps_sum            | quantiles     |           
     | Count of TCP packets                                                    | net_tcp_packets              | counters      |             
     | Count of TCP SYN packets                                                | net_tcp_syn_packets          | counters      |         
     | Top ASNs by IP                                                          | net_top_asn_packets          | top_geo       |         
     | Top GeoIP locations                                                     | net_top_geo_loc_packets      | top_geo       |     
     | Top IPv4 addresses                                                      | net_top_ipv4_packets         | top_ips       |        
     | Top IPv6 addresses                                                      | net_top_ipv6_packets         | top_ips       |        
     | Count of total packets matching the configured filter(s)                | net_total_packets            | counters      |           
     | Count of UDP packets                                                    | net_udp_packets              | counters      |             

## PCAP Metrics
<font size="1">[Check how to activate pcap metrics](/documentation/advanced_policies/#packet-capture-analyzer-pcap)</font>

| Metric                                        | Prometheus Name               |
|-----------------------------------------------|-------------------------------|
| Total wire packets dropped by the interface   | pcap\_if\_drops               |
| Total wire packets dropped by the OS          | pcap\_os\_drops               |
| Total TCP wire packets that failed reassembly | pcap\_tcp\_reassembly\_errors |


## BGP metrics
<font size="1">[Check how to activate bgp metrics](/documentation/advanced_policies/#bgp-analyzer-bgp)</font>

| Metric                                                                                | Prometheus Name                   |
|---------------------------------------------------------------------------------------|-----------------------------------|
| Quantiles of all BGP wire packets before filtering per second                         | bgp\_rates\_events                |
| Count of all BGP wire packets before filtering per second                             | bgp\_rates\_events\_count         |
| Total sum of all BGP wire packets before filtering per second                         | bgp\_rates\_events\_sum           |
| Quantiles of all BGP wire packets (combined ingress and egress) in packets per second | bgp\_rates\_total                 |
| Count of all BGP wire packets (combined ingress and egress) in packets per second     | bgp\_rates\_total\_count          |
| Total sum of all BGP wire packets (combined ingress and egress) in packets per second | bgp\_rates\_total\_sum            |
| Total BGP wire packets that were sampled for deep inspection                          | bgp\_wire\_packets\_deep\_samples |
| Total BGP wire packets events                                                         | bgp\_wire\_packets\_events        |
| Total BGP wire packets seen that did not match the configured filter(s) (if any)      | bgp\_wire\_packets\_filtered      |
| Total BGP packets with message type KEEPALIVE                                         | bgp\_wire\_packets\_keepalive     |
| Total BGP packets with message type NOTIFICATION                                      | bgp\_wire\_packets\_notification  |
| Total BGP packets with message type UPDATE                                            | bgp\_wire\_packets\_update        |
| Total BGP packets with message type OPEN                                              | bgp\_wire\_packets\_open          |
| Total BGP packets with message type ROUTEREFRESH                                      | bgp\_wire\_packets\_routerefresh  |
| Total BGP wire packets matching the configured filter(s)                              | bgp\_wire\_packets\_total         |


## Flow metrics [BETA]
<font size="1">[Check how to activate/deactivate flow metrics](/documentation/advanced_policies/#flow-analyzer-flow-beta)</font>

!!! warning

    Status: `Beta`. The metric names and configuration options may still change


| Metric                                                                                 | Prometheus Name                        | Metric Groups               |
|----------------------------------------------------------------------------------------|----------------------------------------|-----------------------------|
| Conversations cardinality                                                              | flow\_cardinality\_conversations       | cardinality + conversations |
| Destination IP cardinality                                                             | flow\_cardinality\_dst\_ips\_out       | cardinality                 |
| Destination ports cardinality                                                          | flow\_cardinality\_dst\_ports\_out     | cardinality                 |
| Source IP cardinality                                                                  | flow\_cardinality\_src\_ips\_in        | cardinality                 |
| Source ports cardinality                                                               | flow\_cardinality\_src\_ports\_in      | cardinality                 |
| Count of in by bytes                                                                   | flow\_in\_bytes                        | counters + by_bytes         |
| Count of in IPv4 by bytes                                                              | flow\_in\_ipv4\_bytes                  | counters + by_bytes         |
| Count of in IPv4 by packets                                                            | flow\_in\_ipv4\_packets                | counters + by_packets       |
| Count of in IPv6 by bytes                                                              | flow\_in\_ipv6\_bytes                  | counters + by_bytes         |
| Count of in IPv6 by packets                                                            | flow\_in\_ipv6\_packets                | counters + by_packets       |
| Count of in by bytes which are not UDP or TCP                                          | flow\_in\_other\_l4\_bytes             | counters + by_bytes         |
| Count of in by packtes which are not UDP or TCP                                        | flow\_in\_other\_l4\_packets           | counters + by_packets       |
| Count of in by packets                                                                 | flow\_in\_packets                      | counters + by_packets       |
| Count of in TCP by bytes                                                               | flow\_in\_tcp\_bytes                   | counters + by_bytes         |
| Count of in TCP by packets                                                             | flow\_in\_tcp\_packets                 | counters + by_packets       |
| Count of in UDP by bytes                                                               | flow\_in\_udp\_bytes                   | counters + by_bytes         |
| Count of in UDP by packets                                                             | flow\_in\_udp\_packets                 | counters + by_packets       |
| Count of out by bytes                                                                  | flow\_out\_bytes                       | counters + by_bytes         |
| Count of out IPV4 by bytes                                                             | flow\_out\_ipv4\_bytes                 | counters + by_bytes         |
| Count of out IPV4 by packets                                                           | flow\_out\_ipv4\_packets               | counters + by_packets       |
| Count of out IPV6 by bytes                                                             | flow\_out\_ipv6\_bytes                 | counters + by_bytes         |
| Count of out IPV6 by packets                                                           | flow\_out\_ipv6\_packets               | counters + by_packets       |
| Count of out by bytes which are not UDP or TCP                                         | flow\_out\_other\_l4\_bytes            | counters + by_bytes         |
| Count of out by packets which are not UDP or TCP                                       | flow\_out\_other\_l4\_packets          | counters + by_packets       |
| Count of out by packets                                                                | flow\_out\_packets                     | counters + by_packets       |
| Count of out TCP by bytes                                                              | flow\_out\_tcp\_bytes                  | counters + by_bytes         |
| Count of out TCP by packets                                                            | flow\_out\_tcp\_packets                | counters + by_packets       |
| Count of out UDP by bytes                                                              | flow\_out\_udp\_bytes                  | counters + by_bytes         |
| Count of out UDP by packets                                                            | flow\_out\_udp\_packets                | counters + by_packets       |
| Count of total flows records seen that did not match the configured filter(s) (if any) | flow\_records\_filtered                | counters                    |
| Count of total flows records that match the configured filter(s) (if any)              | flow\_records\_flows                   | counters                    |
| Top ASNs by IP by bytes                                                                | flow\_top\_asn\_bytes                  | top_geo + by_bytes          |
| Top ASNs by IP by packets                                                              | flow\_top\_asn\_packets                | top_geo + by_packets        |
| Top source IP addresses and port by bytes                                              | flow\_top\_conversations\_bytes        | conversations + by_bytes    |
| Top source IP addresses and port by packets                                            | flow\_top\_conversations\_packets      | conversations + by_packets  |
| Top GeoIP locations by bytes                                                           | flow\_top\_geo\_loc\_bytes             | top_geo + by_bytes          |
| Top GeoIP locations by packets                                                         | flow\_top\_geo\_loc\_packets           | top_geo + by_packets        |
| Top in destination IP addresses and port by bytes                                      | flow\_top\_in\_dst\ip\_ports\_bytes    | top_ips_ports + by_bytes    |
| Top in destination IP addresses and port by packets                                    | flow\_top\_in\_dst\ip\_ports\_packets  | top_ips_ports + by_packets  |
| Top in destination IP addresses by bytes                                               | flow\_top\_in\_dst\_ips\_bytes         | top_ips + by_bytes          |
| Top in destination IP addresses by packets                                             | flow\_top\_in\_dst\_ips\_packets       | top_ips + by_packets        |
| Top in destination ports by bytes                                                      | flow\_top\_in\_dst\_ports\_bytes       | top_ports + by_bytes        |
| Top in destination ports by packets                                                    | flow\_top\_in\_dst\_ports\_packets     | top_ports + by_packets      |
| Top input interfaces by bytes                                                          | flow\_top\_in\_interfaces\_bytes       | top_interfaces + by_bytes   |
| Top input interfaces by packets                                                        | flow\_top\_in\_interfaces\_packets     | top_interfaces + by_packets |
| Top in source IP addresses and port by bytes                                           | flow\_top\_in\_src\ip\_ports\_bytes    | top_ips_ports + by_bytes    |
| Top in source IP addresses and port by packets                                         | flow\_top\_in\_src\ip\_ports\_packets  | top_ips_ports + by_packets  |
| Top in source IP addresses by bytes                                                    | flow\_top\_in\_src\_ips\_bytes         | top_ips + by_bytes          |
| Top in source IP addresses by packets                                                  | flow\_top\_in\_src\_ips\_packets       | top_ips + by_packets        |
| Top in source ports by bytes                                                           | flow\_top\_in\_src\_ports\_bytes       | top_ports + by_bytes        |
| Top in source ports by packets                                                         | flow\_top\_in\_src\_ports\_packets     | top_ports + by_packets      |
| Top out destination IP addresses and port by bytes                                     | flow\_top\_out\_dst\ip\_ports\_bytes   | top_ips_ports + by_bytes    |
| Top out destination IP addresses and port by packets                                   | flow\_top\_out\_dst\ip\_ports\_packets | top_ips_ports + by_packets  |
| Top out destination IP addresses by bytes                                              | flow\_top\_out\_dst\_ips\_bytes        | top_ips + by_bytes          |
| Top out destination IP addresses by packets                                            | flow\_top\_out\_dst\_ips\_packets      | top_ips + by_packets        |
| Top out destination ports by bytes                                                     | flow\_top\_out\_dst_ports\_bytes       | top_ports + by_bytes        |
| Top out destination ports by packets                                                   | flow\_top\_out\_dst_ports\_packets     | top_ports + by_packets      |
| Top output interfaces by bytes                                                         | flow\_top\_out\_interfaces\_bytes      | top_interfaces + by_bytes   |
| Top output interfaces by packets                                                       | flow\_top\_out\_interfaces\_packets    | top_interfaces + by_packets |
| Top out source IP addresses and port by bytes                                          | flow\_top\_out\_src\ip\_ports\_bytes   | top_ips_ports + by_bytes    |
| Top out source IP addresses and port by packets                                        | flow\_top\_out\_src\ip\_ports\_packets | top_ips_ports + by_packets  |
| Top out source IP addresses by bytes                                                   | flow\_top\_out\_src\_ips\_bytes        | top_ips + by_bytes          |
| Top out source IP addresses by packets                                                 | flow\_top\_out\_src\_ips\_packets      | top_ips + by_packets        |
| Top out source ports by bytes                                                          | flow\_top\_out\_src\_ports\_bytes      | top_ports + by_bytes        |
| Top out source ports by packets                                                        | flow\_top\_out\_src\_ports\_packets    | top_ports + by_packets      |


## Netprobe Metrics [BETA]
<font size="1">[Check how to activate/deactivate netprobe metrics](/documentation/advanced_policies/#netprobe-beta)</font>

!!! warning

    Status: `Beta`. The metric names and configuration options may still change


| Metric                                                                     | Prometheus Name                           | Metric Groups                        |
|----------------------------------------------------------------------------|-------------------------------------------|--------------------------------------|
| Quantiles of Net Probe quantile in microseconds                            | netprobe\_response\_quantiles\_us         | quantiles                            |
| Total sum of Net Probe quantile in microseconds                            | netprobe\_response\_quantiles\_us\_sum    | quantiles                            |
| Count of Net Probe quantile in microseconds                                | netprobe\_response\_quantiles\_us\_count  | quantiles                            |
| Total Net Probe attempts                                                   | netprobe\_attempts                        | counters                             |
| Total Net Probe failures when performed DNS lookup                         | netprobe\_dns\_lookup\_failures           | counters                             |
| Total Net Probe timeout transactions                                       | netprobe\_packets\_timeout                | counters                             |
| Maximum response time measured in the reporting interval                   | netprobe\_response\_max\_us               | counters + (quantiles or histograms) |
| Minimum response time measured in the reporting interval                   | netprobe\_response\_min\_us               | counters + (quantiles or histograms) |
| Total Net Probe successes                                                  | netprobe\_successes                       | counters                             |
| Cumulative counters for the buckets of Net Probe histogram in microseconds | netprobe\_response\_histogram\_us\_bucket | histograms                           |
| Count of events of Net Probe histogram in microseconds                     | netprobe\_response\_histogram\_us\_count  | histograms                           |
