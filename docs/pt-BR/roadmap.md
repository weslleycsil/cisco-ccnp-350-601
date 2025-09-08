---
title: Roadmap
---

# Roadmap — CCNP DCCOR 350-601 (14 semanas)

## Visão geral (Gantt)
```mermaid
gantt
  title Roadmap DCCOR 350-601 (14 semanas)
  dateFormat  YYYY-MM-DD
  axisFormat  %d/%m

  %% Ajuste a data inicial abaixo para o seu início real
  section Fundamentos (Revisão CCNA -> DC)
  STP/VLAN/EtherChannel           :a1, 2025-09-08, 14d
  OSPF/BGP (conceitos)            :a2, after a1, 7d

  section Network em DC (NX-OS)
  vPC/Port-Channel/HSRP/VRRP      :b1, after a2, 14d
  OSPF underlay + BGP overlay     :b2, after b1, 7d

  section VXLAN EVPN
  Conceitos + NVE/VNI/IRB         :c1, after b2, 7d
  EVPN (Route Types, Anycast GW)  :c2, after c1, 7d

  section Compute (UCS)
  UCS Arch/Policies/Profiles      :d1, after c2, 14d

  section Storage Networking
  FC/FCoE/VSAN/Zoning/NPIV        :e1, after d1, 14d

  section Security
  AAA/RBAC/CoPP/ACLs              :f1, after e1, 7d

  section Automation
  NX-API/REST/Ansible/YANG/NETCONF:g1, after f1, 7d

  section Revisão & Prova
  Revisão geral + simulados       :h1, after g1, 14d
```

> Legenda: **S%W** na régua = Semana (S01 = semana 1, etc.). Ajuste as semanas conforme o teu início real.

---

## Dependências (mapa)
```mermaid
flowchart LR
  subgraph Fundamentos
    A[STP/VLAN/EtherChannel]
    B[OSPF/BGP - conceitos]
  end

  subgraph Network em DC
    C[vPC/HSRP/VRRP]
    D[Underlay OSPF]
    E[Overlay BGP]
  end

  subgraph VXLAN EVPN
    F[Conceitos VXLAN<br/>NVE/VNI/IRB]
    G[EVPN Route-Types<br/>Anycast GW]
  end

  subgraph Plataformas
    H[Cisco UCS<br/>Profiles/Policies]
    I[Storage DC<br/>FC/FCoE/VSAN/NPIV]
  end

  subgraph Segurança & Automação
    J[AAA/RBAC/CoPP/ACLs]
    K[NX-API/REST<br/>Ansible/YANG/NETCONF]
  end

  A --> C
  B --> D --> E
  C --> F
  D --> F
  E --> G
  F --> G
  C --> J
  H --> J
  I --> J
  C --> K
  H --> K
  I --> K
```

---

## Checklist de estudo
- [ ] **Fundamentos**: STP, VLAN, EtherChannel, OSPF/BGP (conceitos).  
- [ ] **Network DC**: vPC, HSRP/VRRP, OSPF underlay, BGP overlay.  
- [ ] **VXLAN EVPN**: NVE, VNI, IRB, Route Types (2/5), Anycast Gateway.  
- [ ] **UCS**: Service Profiles, Templates, Policies (BIOS/Boot/vNIC/vHBA).  
- [ ] **Storage**: FC, FCoE, VSAN, Zoning, NPIV, multipathing.  
- [ ] **Security**: AAA/TACACS+, RBAC, CoPP, ACLs.  
- [ ] **Automation**: NX-API/REST, Ansible (NX-OS/UCS), YANG/NETCONF (conceitos).  
- [ ] **Simulados & Errata**: 2 simulados completos + revisão dos erros.
- [ ] Teste