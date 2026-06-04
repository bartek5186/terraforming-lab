# Solar Mesh Bitcoin — an interplanetary optical relay network for cryptographic data

## 1. Executive summary

**Solar Mesh Bitcoin** is a concept for an interplanetary communication network based on laser optical links, mobile heliocentric relays, Lagrange-point hubs, planetary orbiters, lunar infrastructure, and Delay/Disruption Tolerant Networking protocols. Its goal is to enable independent, resilient, and cryptographically verifiable transmission of Bitcoin data and other settlement-layer messages between Earth, the Moon, Mars, and eventually other regions of the Solar System.

The system does not assume faster-than-light communication. The physical limit remains fundamental: electromagnetic signals cannot arrive faster than light in vacuum. The strength of the concept lies elsewhere: availability, redundancy, throughput, resilience against solar occlusion, failures, contact interruptions, and the ability to maintain critical financial-data propagation in an interplanetary environment.

In this architecture, Bitcoin acts as a global interplanetary final settlement layer, while local payment systems such as the Lightning Network, federated settlement systems, or other second-layer protocols can handle fast payments inside a single planet, moon, orbital station, or colony.

## 2. Core idea

Instead of designing a single Earth–Mars link, the system should be designed as a **mobile optical mesh** composed of many types of nodes:

- Earth ground stations,
- Mars ground stations,
- lunar surface stations,
- LEO, MEO, and GEO satellites,
- Moon, Mars, and planetary orbiters,
- relays at Lagrange points,
- heliocentric satellites orbiting the Sun at different orbital radii,
- relay nodes distributed between the orbits of Earth and Mars,
- future nodes around Venus, the asteroid belt, Jupiter, and its moons.

Each node knows its own position, velocity, the ephemerides of other nodes, predicted contact windows, buffer state, energy state, and the quality of possible optical links. Routing is not classic Internet routing. It is space-time routing, where a graph edge exists only during a specific time interval.

The most important rule:

```text
The best route is not always the route with the fewest hops.
The best route is the one that delivers data the earliest under known future contacts.
```

## 3. The speed-of-light constraint

Solar Mesh does not make an Earth–Mars payment instant. If Mars is far from Earth, one-way latency may be many minutes. If the planets are on opposite sides of the Sun, direct communication can become degraded or temporarily unavailable.

The optical mesh helps in other ways:

- routing around solar occlusion,
- increasing system availability,
- shortening individual laser hops, which can improve throughput,
- storing data until the next contact becomes available,
- parallel distribution of blocks and transactions,
- communication with many colonies and stations at once,
- reducing dependence on a single ground station or orbiter.

If a direct Earth–Mars line of sight is available and the link budget is good, a multi-hop route will not be faster than direct transmission. Multiple hops become valuable when the direct link is unavailable, occluded, overloaded, energetically expensive, or weak.

## 4. System topology

The proposed architecture consists of several layers.

### 4.1. Earth local layer

This layer includes:

- optical ground stations,
- RF ground stations as fallback,
- LEO satellites,
- MEO satellites,
- GEO satellites,
- gateways to the classical Internet,
- full Bitcoin nodes,
- Lightning nodes,
- data centers maintaining blockchain and mempool replicas.

The Earth layer is initially the main gateway to today’s Bitcoin network, because most hashpower, exchanges, liquidity infrastructure, and users are located on Earth.

### 4.2. Earth–Moon layer

This layer includes:

- lunar orbiters,
- lunar surface stations,
- Earth-Moon L1 and L2 points,
- relays between Earth, the Moon, and the heliocentric network.

The Moon is the natural first testbed for an interplanetary version of the network. Earth–Moon latency is small compared with Mars, while the operational environment still allows testing optical communication, autonomous routing, contact interruptions, and independent power infrastructure.

### 4.3. Lagrange-point layer

Lagrange points can act as strategic hubs.

Key locations:

- Earth-Sun L4,
- Earth-Sun L5,
- Mars-Sun L4,
- Mars-Sun L5,
- Earth-Moon L1,
- Earth-Moon L2,
- potentially Lagrange points of other planets and moons.

L4 and L5 are especially attractive as long-term infrastructure regions because they are more stable than L1 and L2. L1 and L2 are useful as gateways, observatories, and transition points, but they require more active station-keeping.

### 4.4. Heliocentric relay rings

The most important part of the concept is a network of satellites orbiting the Sun at different orbital radii. Instead of placing relays in a single line between Earth and Mars, the system should use multiple rings between their orbits.

Example layout:

```text
Ring A: 1.05 AU
Ring B: 1.15 AU
Ring C: 1.25 AU
Ring D: 1.35 AU
Ring E: 1.45 AU
Ring F: 1.52 AU, near the orbit of Mars
```

Each ring can contain many satellites distributed angularly around the Sun. Nodes are not static relative to Earth and Mars, but their motion is predictable. The system uses ephemerides to plan future contacts.

Example logical diagram:

```mermaid
graph LR
    Earth[Earth] --> EM[Earth-Moon Relay]
    EM --> ES4[Earth-Sun L4/L5]
    ES4 --> R1[Ring 1.15 AU]
    R1 --> R2[Ring 1.25 AU]
    R2 --> R3[Ring 1.35 AU]
    R3 --> MS4[Mars-Sun L4/L5]
    MS4 --> MO[Mars Orbiter]
    MO --> Mars[Mars]
```

## 5. Distance X between nodes

There should not be one global value of X. Node spacing should depend on the link class, required throughput, launch cost, available energy, optical terminal size, and desired redundancy.

Suggested classes:

| Class | Approximate node spacing | Use case |
|---|---:|---|
| Local | 1,000–100,000 km | orbiters, moons, orbital stations |
| Planetary | 100,000–1,000,000 km | regions around planets and moons |
| Regional | 1–5 million km | transition from planetary to heliocentric space |
| Dense interplanetary mesh | 5–25 million km | high throughput and redundancy |
| Sparse backbone | 25–100 million km | cheaper backbone network |
| Direct deep-space | 100–400+ million km | fallback, broadcast, emergency mode |

Bitcoin itself does not require massive throughput. Block headers, transactions, compact block relay, and Merkle proofs are small. A dense mesh becomes justified when the same infrastructure also supports interplanetary Internet, telemetry, exchanges, scientific data, streaming, colony communication, and data archiving.

## 6. Solar Mesh node

Each node should act as an autonomous router, data store, and cryptographic validator.

Example structure:

```text
SolarMeshNode
├── Optical Terminal A
├── Optical Terminal B
├── Optical Terminal C
├── RF fallback
├── Ephemeris Engine
├── Contact Planner
├── DTN Bundle Protocol Node
├── Contact Graph Routing Engine
├── Bitcoin Relay Module
├── Block/Header Validator
├── Mempool Cache
├── UTXO Snapshot Cache
├── Priority Queue
├── Store-and-Forward Buffer
├── Clock Synchronization Module
├── Energy Management Module
├── Fault Detection Module
└── Autonomous Operations Controller
```

A node should support at least three functions:

1. **Optical communication** — directional high-throughput laser links.
2. **Store-and-forward** — storing packets until the next contact becomes available.
3. **Cryptographic validation** — rejecting invalid Bitcoin data and propagating only valid structures.

## 7. Space-time routing

Solar Mesh requires routing based on predicted contacts. Each link has a start time, end time, throughput, propagation delay, loss risk, and energy cost.

Graph model:

```text
Node = satellite, station, orbiter, Lagrange-point hub, heliocentric relay
Edge = possible optical connection during [t_start, t_end]
Weight = propagation_delay + scheduled_wait + queue_delay + acquisition_time + risk_penalty
```

Route-selection metric:

```text
cost =
  light_time
+ scheduled_wait_time
+ pointing_acquisition_time
+ queue_delay
+ retransmission_risk
+ solar_occlusion_penalty
+ energy_penalty
+ priority_adjustment
```

For critical data, the system should choose the route with the earliest delivery time, not necessarily the route with the fewest hops. For non-critical data, it may choose a route that is cheaper energetically or consumes less link capacity.

## 8. Transport protocol

The core transport model should follow Delay/Disruption Tolerant Networking and Bundle Protocol concepts. Classic TCP/IP is insufficient because it assumes relatively stable links, short delays, and quick retransmission. In space, links are intermittent, delays are large, and contact between nodes may exist only in specific time windows.

Recommended model:

```text
Bitcoin / Lightning / settlement data
        ↓
Priority-aware application adapter
        ↓
DTN Bundle Protocol
        ↓
Contact Graph Routing
        ↓
Optical link layer
        ↓
Laser terminal
```

## 9. Bitcoin layer

The safest approach is to avoid changing Bitcoin L1. Solar Mesh acts as a new transport layer.

The system should prioritize data as follows:

| Priority | Data | Role |
|---|---|---|
| P0 | Block headers | fastest information about chain state |
| P1 | High-fee transactions | rapid propagation of valuable transactions |
| P2 | Compact blocks | efficient block reconstruction |
| P3 | Full blocks | full synchronization |
| P4 | Lightning gossip and watchtower data | support for payment layers |
| P5 | UTXO snapshots and archive data | low-priority data |

Bitcoin data is cryptographically verifiable. Transport nodes do not need to be fully trusted, because the receiver can independently verify:

- block-header proof-of-work,
- block structure correctness,
- transaction signatures,
- Merkle proofs,
- consistency with the local UTXO set,
- compact block reconstruction consistency.

## 10. Mining and latency

Interplanetary mining is hard. Bitcoin has an average block interval of about 10 minutes. If Mars receives information about an Earth-mined block after many minutes, a Martian miner may continue mining on a stale chain tip for a meaningful period of time. This increases stale/orphan block risk.

A realistic economic model therefore looks like this:

```text
Earth: main liquidity, most hashpower, global exchange infrastructure
Mars: local payments, local Lightning channels, local financial services
Bitcoin L1: interplanetary final settlement
Solar Mesh: cryptographic data transport
```

Mars can use Bitcoin, but it should not assume the same position in global mining as nodes located on Earth while most hashpower remains inside the Earth communication domain.

## 11. Lightning and local payment domains

The Lightning Network or similar second-layer systems are a natural complement to Solar Mesh.

Model:

```text
Mars Colony A ↔ Mars Colony B: fast local payments
Mars ↔ Earth: slower settlements and channel synchronization
Earth ↔ Moon: nearly real-time compared with Mars
```

Local domains can operate quickly because latency within one planet or moon is relatively small. Interplanetary settlements are slower, but they can be performed periodically, similar to final settlement between banks or exchanges in classical financial systems.

## 12. Scenario: transaction from Mars to Earth

```text
1. A user on Mars signs a transaction.
2. A local Martian node validates the transaction.
3. The transaction enters the Martian mempool.
4. A Mars orbiter receives the packet and sends it to the nearest Solar Mesh node.
5. Contact Graph Routing selects the earliest-delivery route.
6. The packet crosses one or more heliocentric relays.
7. An Earth-Sun relay or GEO relay sends the packet to an Earth ground station.
8. An Earth Bitcoin Gateway propagates the transaction to the global Bitcoin network.
9. The transaction enters the mempools of Earth-based miners.
10. Once the transaction is mined, confirmation data returns to Mars as a header, compact block, and, if needed, a full block.
```

## 13. Scenario: block from Earth to Mars

```text
1. A miner on Earth finds a new block.
2. The Earth gateway immediately sends the block header as P0.
3. In parallel, a compact block is sent as P2.
4. Solar Mesh nodes select the route to Mars.
5. A Martian relay receives the header and checks proof-of-work.
6. A Martian node tries to reconstruct the block from its local mempool.
7. Missing transactions are requested as separate packets.
8. After full validation, the block becomes part of the local chain view.
```

## 14. Security

Solar Mesh should assume that some relays may be unreliable, malicious, damaged, or compromised. Security is based on several layers:

- cryptographic verifiability of Bitcoin data,
- multi-path propagation,
- signed control messages,
- node reputation and health state,
- route redundancy,
- DTN packet integrity checks,
- local rejection of invalid blocks and transactions,
- separation of transport from financial trust.

The key rule:

```text
You do not need to trust the relay to verify Bitcoin data.
```

A relay can delay, drop, or censor a packet, but it cannot forge a valid block or transaction without breaking the cryptography and proof-of-work mechanism.

## 15. Deployment phases

### Phase 1: Earth–Moon

- test laser relay for Bitcoin data,
- full nodes on Earth and near the Moon,
- DTN bundle transfer,
- block header and compact block validation,
- experimental Lightning channel with space latency.

### Phase 2: Earth–Mars through existing orbiters

- Earth gateway,
- Mars orbiter,
- Martian full node,
- propagation of block headers and transactions,
- analysis of latency and mempool behavior.

### Phase 3: Lagrange points

- Earth-Sun L4/L5 hubs,
- Mars-Sun L4/L5 hubs,
- routing around the Sun,
- data buffering during solar conjunction.

### Phase 4: Heliocentric relay rings

- several orbits between 1.0 AU and 1.52 AU,
- dozens of relays per ring,
- predictive routing based on ephemerides,
- multi-path propagation of critical packets.

### Phase 5: Solar System Internet

- expansion to Venus,
- expansion to the asteroid belt,
- hubs near Jupiter and its moons,
- full interplanetary settlement and communication network.

## 16. Minimal research product

A minimal MVP does not require hundreds of satellites. The first step can be a software and laboratory simulation.

MVP elements:

- orbital simulator,
- ephemeris generator,
- contact graph,
- earliest-arrival routing,
- DTN module,
- Bitcoin adapter,
- packet prioritization,
- Earth–Moon and Earth–Mars latency simulation,
- direct link vs mesh comparison,
- stale/orphan risk analysis for interplanetary mining.

A production backend could be divided into modules such as:

```text
controller: API, simulation configuration, dashboard
service: routing, contact planning, packet scheduling
store: ephemerides, packets, simulation results, metrics
model: node, edge, contact, bundle, bitcoin_message
```

## 17. Main risks

| Risk | Description | Possible mitigation |
|---|---|---|
| Physical latency | The speed of light cannot be bypassed | local payment layers, L1 final settlement |
| Solar conjunction | The Sun blocks or degrades the direct path | L4/L5 hubs, heliocentric rings, DTN |
| High infrastructure cost | Launching and maintaining satellites is expensive | phased deployment, dual-use general communications |
| Laser precision | Requires accurate pointing/acquisition/tracking | shorter hops, multi-beam terminals |
| Energy | Nodes far from the Sun have less solar power | route optimization, batteries, larger arrays |
| Relay security | Nodes may censor or delay packets | multi-path routing, cryptographic verification |
| Interplanetary mining | Long delays increase stale block risk | local L2 payments, L1 as settlement |

## 18. Conclusion

Solar Mesh Bitcoin is not a method for making Bitcoin instant between planets. It is a method for creating a **resilient, autonomous, optical transport infrastructure for cryptographic data across the Solar System**.

The strongest interpretation of the idea is:

```text
Bitcoin = interplanetary final settlement layer
Lightning / L2 = local fast payments
Solar Mesh = optical, predictive, resilient data transport
DTN = survival protocol for delayed and disrupted environments
```

Over the long term, such infrastructure could become one of the foundations of an interplanetary economy: an independent settlement system operating across planets, states, telecom operators, and local infrastructure failures.

## 19. Sources and technical directions

- NASA — Delay/Disruption Tolerant Networking: https://www.nasa.gov/communicating-with-missions/delay-disruption-tolerant-networking/
- IETF RFC 9171 — Bundle Protocol Version 7: https://datatracker.ietf.org/doc/rfc9171/
- NASA — Deep Space Optical Communications: https://www.nasa.gov/mission/deep-space-optical-communications-dsoc/
- NASA — Laser Communications Relay Demonstration: https://www.nasa.gov/directorates/stmd/tech-demo-missions-program/laser-communications-relay-demonstration-lcrd-overview/
- ESA — Lagrange points: https://www.esa.int/Enabling_Support/Operations/What_are_Lagrange_points
- Bitcoin BIP152 — Compact Block Relay: https://bips.dev/152/
- Blockstream Satellite: https://blockstream.com/satellite/
