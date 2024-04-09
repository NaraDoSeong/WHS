네트워크 기초 PCAP Programming


  printf("  IP: %18s", inet_ntoa(ip->iph_sourceip));
  print_right(3,2);
  printf("%s\n", inet_ntoa(ip->iph_destip));
  
  printf(" MAC: %02x:%02x:%2uc:%02x:%02x:%02x", eth->ether_shost[0], eth->ether_shost[1], eth->ether_shost[2], eth->ether_shost[3], eth->ether_shost[4], eth->ether_shost[5]);
  print_right(3,2);
  printf("%02X:%02X:%02X:%02X:%02X:%02X\n", eth->ether_dhost[0], eth->ether_dhost[1], eth->ether_dhost[2], eth->ether_dhost[3], eth->ether_dhost[4], eth->ether_dhost[5]);
  
  printf("Port: %18d", ntohs(tcp->tcp_sport));  
  print_right(3,3);
  printf("%d\n", ntohs(tcp->tcp_dport));
  
  print_line(70);

  -->
  
  printf("  IP: %18s", inet_ntoa(ip->iph_sourceip));
  print_right();
  printf("%s\n", inet_ntoa(ip->iph_destip));
  
  printf(" MAC: %02x:%02x:%2uc:%02x:%02x:%02x", eth->ether_shost[0], eth->ether_shost[1], eth->ether_shost[2], eth->ether_shost[3], eth->ether_shost[4], eth->ether_shost[5]);
  print_right();
  printf("%02X:%02X:%02X:%02X:%02X:%02X\n", eth->ether_dhost[0], eth->ether_dhost[1], eth->ether_dhost[2], eth->ether_dhost[3], eth->ether_dhost[4], eth->ether_dhost[5]);
  
  printf("Port: %18d", ntohs(tcp->tcp_sport));  
  print_right();
  printf("%d\n", ntohs(tcp->tcp_dport));
  
  print_line(70);

  함수 변경과정 중에 print_right()함수의 매개변수 부분을 제거하지 않은 오류가 있었습니다. Ubuntu 22.04 버전 gcc에서 처리를 잘해주어서 오류가 나지 않아 프로그램은 정상적으로 동작합니다.
