# SPDX-License-Identifier: LGPL-2.1-or-later

sources = files('''
        netdev/bareudp.c
        netdev/bareudp.h
        netdev/batadv.c
        netdev/batadv.h
        netdev/bond.c
        netdev/bond.h
        netdev/bridge.c
        netdev/bridge.h
        netdev/dummy.c
        netdev/dummy.h
        netdev/ifb.c
        netdev/ifb.h
        netdev/ipoib.c
        netdev/ipoib.h
        netdev/ipvlan.c
        netdev/ipvlan.h
        netdev/macvlan.c
        netdev/macvlan.h
        netdev/netdev.c
        netdev/netdev.h
        netdev/nlmon.c
        netdev/nlmon.h
        netdev/tunnel.c
        netdev/tunnel.h
        netdev/tuntap.c
        netdev/tuntap.h
        netdev/vcan.c
        netdev/vcan.h
        netdev/veth.c
        netdev/veth.h
        netdev/vlan.c
        netdev/vlan.h
        netdev/vrf.c
        netdev/vrf.h
        netdev/vxlan.c
        netdev/vxlan.h
        netdev/geneve.c
        netdev/geneve.h
        netdev/vxcan.c
        netdev/vxcan.h
        netdev/wireguard.c
        netdev/wireguard.h
        netdev/netdevsim.c
        netdev/netdevsim.h
        netdev/fou-tunnel.c
        netdev/fou-tunnel.h
        netdev/l2tp-tunnel.c
        netdev/l2tp-tunnel.h
        netdev/macsec.c
        netdev/macsec.h
        netdev/xfrm.c
        netdev/xfrm.h
        networkd-address-generation.c
        networkd-address-generation.h
        networkd-address-label.c
        networkd-address-label.h
        networkd-address-pool.c
        networkd-address-pool.h
        networkd-address.c
        networkd-address.h
        networkd-bridge-fdb.c
        networkd-bridge-fdb.h
        networkd-bridge-mdb.c
        networkd-bridge-mdb.h
        networkd-bridge-vlan.c
        networkd-bridge-vlan.h
        networkd-can.c
        networkd-can.h
        networkd-conf.c
        networkd-conf.h
        networkd-dhcp-common.c
        networkd-dhcp-common.h
        networkd-dhcp-prefix-delegation.c
        networkd-dhcp-prefix-delegation.h
        networkd-dhcp-server-bus.c
        networkd-dhcp-server-bus.h
        networkd-dhcp-server-static-lease.c
        networkd-dhcp-server-static-lease.h
        networkd-dhcp-server.c
        networkd-dhcp-server.h
        networkd-dhcp4.c
        networkd-dhcp4.h
        networkd-dhcp6.c
        networkd-dhcp6.h
        networkd-ipv4acd.c
        networkd-ipv4acd.h
        networkd-ipv4ll.c
        networkd-ipv4ll.h
        networkd-ipv6-proxy-ndp.c
        networkd-ipv6-proxy-ndp.h
        networkd-json.c
        networkd-json.h
        networkd-link-bus.c
        networkd-link-bus.h
        networkd-link.c
        networkd-link.h
        networkd-lldp-rx.c
        networkd-lldp-rx.h
        networkd-lldp-tx.c
        networkd-lldp-tx.h
        networkd-manager-bus.c
        networkd-manager-bus.h
        networkd-manager.c
        networkd-manager.h
        networkd-ndisc.c
        networkd-ndisc.h
        networkd-neighbor.c
        networkd-neighbor.h
        networkd-radv.c
        networkd-radv.h
        networkd-network-bus.c
        networkd-network-bus.h
        networkd-network.c
        networkd-network.h
        networkd-nexthop.c
        networkd-nexthop.h
        networkd-queue.c
        networkd-queue.h
        networkd-route-util.c
        networkd-route-util.h
        networkd-route.c
        networkd-route.h
        networkd-routing-policy-rule.c
        networkd-routing-policy-rule.h
        networkd-setlink.c
        networkd-setlink.h
        networkd-speed-meter.c
        networkd-speed-meter.h
        networkd-sriov.c
        networkd-sriov.h
        networkd-state-file.c
        networkd-state-file.h
        networkd-sysctl.c
        networkd-sysctl.h
        networkd-util.c
        networkd-util.h
        networkd-wifi.c
        networkd-wifi.h
        tc/cake.c
        tc/cake.h
        tc/codel.c
        tc/codel.h
        tc/drr.c
        tc/drr.h
        tc/ets.c
        tc/ets.h
        tc/fifo.c
        tc/fifo.h
        tc/fq.c
        tc/fq.h
        tc/fq-codel.c
        tc/fq-codel.h
        tc/fq-pie.c
        tc/fq-pie.h
        tc/gred.c
        tc/gred.h
        tc/hhf.c
        tc/hhf.h
        tc/htb.c
        tc/htb.h
        tc/netem.c
        tc/netem.h
        tc/pie.c
        tc/pie.h
        tc/qdisc.c
        tc/qdisc.h
        tc/qfq.c
        tc/qfq.h
        tc/sfb.c
        tc/sfb.h
        tc/sfq.c
        tc/sfq.h
        tc/tbf.c
        tc/tbf.h
        tc/tc-util.c
        tc/tc-util.h
        tc/tc.c
        tc/tc.h
        tc/tclass.c
        tc/tclass.h
        tc/teql.c
        tc/teql.h
'''.split())

systemd_networkd_sources = files('networkd.c')

systemd_networkd_wait_online_sources = files('''
        wait-online/link.c
        wait-online/link.h
        wait-online/manager.c
        wait-online/manager.h
        wait-online/wait-online.c
'''.split())

networkctl_sources = files('networkctl.c')

network_generator_sources = files('''
        generator/main.c
        generator/network-generator.c
        generator/network-generator.h
'''.split())

sources += custom_target(
        'networkd-gperf.c',
        input : 'networkd-gperf.gperf',
        output : 'networkd-gperf.c',
        command : [gperf, '@INPUT@', '--output-file', '@OUTPUT@'])

sources += custom_target(
        'networkd-network-gperf.c',
        input : 'networkd-network-gperf.gperf',
        output : 'networkd-network-gperf.c',
        command : [gperf, '@INPUT@', '--output-file', '@OUTPUT@'])

sources += custom_target(
        'netdev-gperf.c',
        input : 'netdev/netdev-gperf.gperf',
        output : 'netdev-gperf.c',
        command : [gperf, '@INPUT@', '--output-file', '@OUTPUT@'])

if get_option('link-networkd-shared')
        networkd_link_with = [libshared]
else
        networkd_link_with = [libsystemd_static,
                              libshared_static,
                              libbasic_gcrypt]
endif

network_includes = [libsystemd_network_includes, include_directories(['.', 'netdev', 'tc'])]

libnetworkd_core = static_library(
        'networkd-core',
        sources,
        include_directories : network_includes,
        link_with : networkd_link_with,
        build_by_default : false)

if conf.get('ENABLE_NETWORKD') == 1
        install_data('org.freedesktop.network1.conf',
                     install_dir : dbuspolicydir)
        install_data('org.freedesktop.network1.service',
                     install_dir : dbussystemservicedir)
        install_data('org.freedesktop.network1.policy',
                     install_dir : polkitpolicydir)
        if install_polkit
                install_data('systemd-networkd.rules',
                             install_dir : polkitrulesdir)
        endif
        if install_polkit_pkla
                install_data('systemd-networkd.pkla',
                             install_dir : polkitpkladir)
        endif

        if install_sysconfdir_samples
                install_data('networkd.conf',
                             install_dir : pkgsysconfdir)
        endif
endif

fuzzers += [
        [['src/network/fuzz-netdev-parser.c'],
         [libnetworkd_core,
          libsystemd_network,
          networkd_link_with],
         [threads],
         network_includes],

        [['src/network/fuzz-network-parser.c'],
         [libnetworkd_core,
          libsystemd_network,
          networkd_link_with],
         [threads],
         network_includes],
]

tests += [
        [['src/network/test-networkd-address.c'],
         [libnetworkd_core,
          libsystemd_network],
         [],
         network_includes],

        [['src/network/test-networkd-conf.c'],
         [libnetworkd_core,
          libsystemd_network],
         [],
         network_includes],

        [['src/network/test-networkd-util.c'],
         [libnetworkd_core,
          libsystemd_network],
         [],
         network_includes],

        [['src/network/test-network.c'],
         [libnetworkd_core,
          libsystemd_network],
         [threads],
         network_includes],

        [['src/network/test-network-tables.c'],
         [libnetworkd_core,
          libsystemd_network],
         [threads],
         network_includes],

        [['src/network/generator/test-network-generator.c',
          'src/network/generator/network-generator.c',
          'src/network/generator/network-generator.h']],
]
