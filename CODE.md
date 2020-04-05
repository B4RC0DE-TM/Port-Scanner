# TEAMEXPLOIT-Scanner-Script-only-TCP-ports
This was my first project and public created in 2018 in the language that I use the most "Perl" about a script that can scan real-time TCP ports in considerable time, although it was recently improved to scan and save ports found in a TXT file. Enjoy the beta of our script
 
 
 Code:
 
 
 #!/usr/bin/perl

use strict;
use warnings;
use IO::Socket::INET;

  my $length = scalar(@ARGV);
  
  if ( $length != 3 && $length != 10 )
  {
    print "\n[>>Ip<<] [>>Comienzo<<] [>>Termino<<] [>>Tiempo=1<<]  #Script by B4RC0DE EXPOSED #TEAMEXPLOITT #[Crasher]#
#############################################################################
                    ---------                                        
   ¦¦¦¦¦¦¦¦¦¦¦    ¦         ¦     ¦¦¦¦¦¦¦¦        ¦¦¦¦¦¦¦¦   ¦¦¦¦¦¦¦¦¦¦     
 ¦           ¦   ¦  -------     ¦        ¦      ¦        ¦ ¦          ¦
   ----   ----   ¦   ¦          ¦    --    ¦     ¦         ¦           ¦
      ¦   ¦      ¦   ¦         ¦    ¦  ¦    ¦   ¦                       ¦   
      ¦   ¦      ¦   -------  ¦     ----     ¦ ¦         ¦¦  ¦¦          ¦
      ¦   ¦      ¦          ¦ ¦              ¦ ¦        ¦  ¦¦  ¦         ¦
      ¦   ¦      ¦          ¦ ¦              ¦ ¦       ¦        ¦        ¦
      ¦   ¦      ¦   -------  ¦     ----     ¦ ¦       |        ¦        ¦ 
      ¦   ¦      ¦   ¦        ¦    ¦    ¦    ¦ ¦       |        ¦        ¦
      ¦   ¦      ¦    ------  ¦    ¦    ¦    ¦ ¦       |        ¦        ¦
      ¦   ¦       ¦         ¦ ¦    ¦    ¦    ¦ ¦       |        ¦        ¦
      ¦   ¦       ¦---------  ¦    ¦    ¦    ¦ ¦       |        ¦        ¦
       ¦¦¦                     ----      ----   -------          -------- 
##############################################################################  
  ¦¦¦¦¦¦¦¦¦¦¦¦¦                    ---------    ---------------   ---- 
 ¦            ¦  ---         --   ¦    ---  ¦  ¦               ¦ ¦    ¦
 ¦    --------  ¦   ¦       ¦   ¦   ¦ ¦   ¦  ¦ ¦----      -----  ¦    ¦
 ¦    ¦          ¦   ¦     ¦   ¦   ¦   ¦   ¦  ¦     ¦    ¦       ¦    ¦
 ¦     ¦          ¦   ¦  ¦    ¦    ¦    ---  ¦      ¦    ¦       ¦    ¦
  ¦    ------      ¦   ¦¦    ¦     ¦        ¦       ¦    ¦       ¦    ¦
 ¦           ¦      ¦      ¦       ¦   ¦----        ¦    ¦       ¦    ¦
 ¦     ------       ¦  ¦¦  ¦       ¦   ¦            ¦    ¦       ¦    ¦
 ¦     ¦           ¦   ¦ ¦   ¦     ¦   ¦            ¦    ¦       ¦    ¦
 ¦      ¦¦¦¦¦¦    ¦   ¦   ¦   ¦    ¦   ¦            ¦    ¦       ¦    ------
 ¦            ¦  ¦   ¦     ¦   ¦   ¦   ¦            ¦    ¦       ¦          ¦
  ¦¦¦¦¦¦¦¦¦¦¦¦    ---       ---     ---              ----         ----------
##############################################################################
 Ejemplo: perl ExploitTeam.pl 45.35.1.114 25565 50000 1\n";
    exit;
  }
  
  my $host = $ARGV[0];
  my $start = $ARGV[1];
  my $end = $ARGV[2];
  my $timeout = 0.5;
  
  if ( $ARGV[3] )
  {
    $timeout = $ARGV[3];
  }
  
  print "\nConexion a ".$host." - Tiempo ".$timeout."\n\n";
  my $response;
  my $port;
  
  for ( $port = $start ; $port <= $end ; $port++ )
  {
    $response = IO::Socket::INET->new(
    PeerAddr => $host,
    PeerPort => $port,
    Proto => "tcp",
    Timeout => $timeout
    );
    
    if ( $response )
    {
      print "Puerto ".$port." : ---#####[Puerto][Vulnerable]#####---\n";
    }
    else
    {
      print "Puerto ".$port." : <--------------- [Cerrado] D:\n";
    }
}
