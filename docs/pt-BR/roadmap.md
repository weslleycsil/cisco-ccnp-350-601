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

  section Fundamentos
  STP/VLAN/EtherChannel            :a1, 2025-09-08, 2w
  OSPF/BGP                         :a2, after a1, 1w

  section Network em DC (NX-OS)
  vPC/Port-Channel/HSRP/VRRP       :b1, after a2, 2w
  OSPF underlay + BGP overlay      :b2, after b1, 1w

  section VXLAN EVPN
  Conceitos + NVE/VNI/IRB          :c1, after b2, 1w
  EVPN (Route Types, Anycast GW)   :c2, after c1, 1w

  section Compute (UCS)
  UCS Arch/Policies/Profiles       :d1, after c2, 2w
  Intersight + Virtualização HW    :d2, after d1, 1w

  section Storage
  FC/FCoE/Zoning/NPIV              :e1, after d2, 2w
  iSCSI/NFS/NVMe-oF                :e2, after e1, 1w

  section Segurança
  AAA/RBAC/Segurança em NX-OS      :f1, after e2, 1w
  ACI Tenants/BD/EPG/Contracts     :f2, after f1, 1w

  section Automação
  NX-API/UCS API/Intersight API    :g1, after f2, 1w
  Ansible/Python/YANG/JSON/XML     :g2, after g1, 1w

  section Revisão Final
  Revisão + Labs + Dumps           :h1, after g2, 1w
```

> Legenda: **S%W** na régua = Semana (S01 = semana 1, etc.). Ajuste as semanas conforme o teu início real.

---

## Visão por módulos

### Fundamentos

```mermaid
%%{init: {"theme": "default", "gantt": {"titleTopMargin":25, "barHeight":30, "barGap":10, "fontSize":16, "sectionFontSize":18, "numberSectionStyles":4, "axisFormat": "S%W"}, "themeVariables": {"fontSize":"18px"}} }%%
gantt
    title Fundamentos (Revisão CCNA -> DC)
    dateFormat  YYYY-MM-DD
    axisFormat  %d/%m
    STP / VLAN / EtherChannel    :a1, 2025-09-08, 1w
    OSPF / BGP (conceitos)       :a2,  after a1, 1w
```

### Network em DC (NX-OS)

```mermaid
%%{init: {"theme": "default", "gantt": {"titleTopMargin":25, "barHeight":30, "barGap":10, "fontSize":16, "sectionFontSize":18, "numberSectionStyles":4, "axisFormat": "S%W"}, "themeVariables": {"fontSize":"18px"}} }%%
gantt
    title Network em DC (NX-OS)
    dateFormat  YYYY-MM-DD
    axisFormat  %d/%m
    vPC / Port-Channel / HSRP / VRRP    :b1, 2025-09-22, 1w
    OSPF underlay                       :b2, after b1, 1w
    BGP overlay                         :b3, after b2, 1w
    VXLAN conceitos + NVE/VNI/IRB       :b4, after b3, 1w
    EVPN (Route Types, Anycast GW)      :b5, after b4, 1w
```

### Compute (UCS)

```mermaid
%%{init: {"theme": "default", "gantt": {"titleTopMargin":25, "barHeight":30, "barGap":10, "fontSize":16, "sectionFontSize":18, "numberSectionStyles":4, "axisFormat": "S%W"}, "themeVariables": {"fontSize":"18px"}} }%%
gantt
    title Compute (UCS)
    dateFormat  YYYY-MM-DD
    axisFormat  %d/%m
    UCS Architecture / Fabric Interconnects   :c1, 2025-10-27, 1w
    Service Profiles / Pools / Policies       :c2, after c1, 1w
    Intersight + Virtualização HW             :c3, after c2, 1w
```

### Storage

```mermaid
%%{init: {"theme": "default", "gantt": {"titleTopMargin":25, "barHeight":30, "barGap":10, "fontSize":16, "sectionFontSize":18, "numberSectionStyles":4, "axisFormat": "S%W"}, "themeVariables": {"fontSize":"18px"}} }%%
gantt
    title Storage
    dateFormat  YYYY-MM-DD
    axisFormat  %d/%m
    FC / FCoE / Zoning / NPIV      :d1, 2025-09-22, 1w
    iSCSI                          :d2, after d1, 0.5w
    NFS                            :d3, after d2, 0.5w
    NVMe-oF                        :d4, after d3, 1w
```

### Segurança

```mermaid
%%{init: {"theme": "default", "gantt": {"titleTopMargin":25, "barHeight":30, "barGap":10, "fontSize":16, "sectionFontSize":18, "numberSectionStyles":4, "axisFormat": "S%W"}, "themeVariables": {"fontSize":"18px"}} }%%
gantt
    title Segurança
    dateFormat  YYYY-MM-DD
    axisFormat  %d/%m
    AAA / RBAC em NX-OS/UCS        :e1, 2025-09-22, 0.5w
    Segurança em NX-OS             :e2, after e1, 0.5w
    ACI Tenants / BD / EPG / Contracts :e3, after e2, 1w
```

### Automação

```mermaid
%%{init: {"theme": "default", "gantt": {"titleTopMargin":25, "barHeight":30, "barGap":10, "fontSize":16, "sectionFontSize":18, "numberSectionStyles":4, "axisFormat": "S%W"}, "themeVariables": {"fontSize":"18px"}} }%%
gantt
    title Automação
    dateFormat  YYYY-MM-DD
    axisFormat  %d/%m
    NX-API / UCS API / Intersight API   :f1, 2025-09-22, 0.5w
    Ansible / Python / YANG / JSON      :f2, after f1, 0.5w
```


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