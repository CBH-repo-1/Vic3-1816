# India And Maratha Accuracy Pass

This file records the approved deeper 1816 backdate for the Maratha/BIC/Central India layer and the follow-up combined India frontier cleanup.

## Implemented Scope

Implemented in `common/history/states/99_cow_1816_india_states.txt`:

| State | 1836 vanilla setup | 1816 mod setup |
| --- | --- | --- |
| `STATE_PUNJAB` | `PAN` and `BHW` | `PAN`, `BHW`, and playable `V10` Multan |
| `STATE_ASSAM` | `BIC`, `ASM`, `NGA`, `MNP`, `TIP`, `KKI`, and `MGH` | Direct `BIC` ownership removed; Brahmaputra/Gauhati/Jorhat area restored to `ASM`; Imphal hub moved to `MNP` |
| `STATE_GUJARAT` | `BER`, `KUT`, `POR`, Gujarat minors, direct `BIC` Ahmedabad block, `JUN`, and `BHV` | Ahmedabad block moved to `BER`; compact Surat port hook moved to `BIC`; Kathiawar minors preserved |
| `STATE_CENTRAL_PROVINCES` | `BIC`, `NAG`, `HYD`, and `BAS` split | Direct `BIC` ownership removed; former Company Saugor/Nerbudda provinces split between `SAT` Peshwa and `NAG` Nagpur |

Implemented in `common/history/diplomacy/99_cow_1816_india_subjects.txt`:

- Remove premature `BIC -> BAS` puppet pact and stale BIC service exemption.
- Add `NAG -> BAS` tributary pact.
- Remove premature `BIC` puppet pacts and stale service exemptions for `BHO`, `MEW`, `JAI`, `JOD`, `BIK`, `JAS`, and `KOT`.
- Remove premature `BIC -> ASM` and `BIC -> MNP` puppet pacts and stale service exemptions.
- Add `BIC -> TIP` protectorate.
- Downgrade Gujarat/Kathiawar minor states `KUT`, `IDA`, `NAW`, `DHA`, `JUN`, `BHV`, and `PLP` from hard `BIC` puppets to lighter `BIC` protectorates.
- Add `KAB -> KAS` and `KAB -> V10` tributaries.
- Preserve earlier Maratha loosening: `NAG`, `IND`, and `GWA` are outside hard Company subjection; `SAT` and `BER` use lighter `BIC` protectorate treatment.
- Keep `ALW` and `PTA` under British influence for now because their British ties predate the 1816 start.

## Rationale

- Saugor and Nerbudda direct Company control is a post-1817/1818 Third Anglo-Maratha War settlement.
- Bastar fits better as a Nagpur-linked tributary in 1816 than as a direct Company puppet.
- Most Rajputana/Bhopal British protectorate alignment belongs to the 1817-1818 Pindari/Maratha campaign, not the January 1, 1816 start.
- Multan was not yet conquered by the Sikh Empire in 1816.
- Kashmir was not yet Sikh-held, while Ladakh can remain independent at this abstraction level.
- Assam and Manipur should not start as Company puppets before the First Anglo-Burmese War and Treaty of Yandabo settlement.
- Ahmedabad/Gujarat should not copy the post-1817 Company settlement; Baroda gets the inland Ahmedabad block while the Company keeps a Surat port hook.

## Follow-Up

- `V10` Multan has a starter army in `common/history/military_formations/05_cow_1816_india_formations.txt`.
- Pops, buildings/resources, laws/governments, and claims still need their own passes.
