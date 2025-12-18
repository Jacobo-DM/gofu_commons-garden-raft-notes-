flowchart TB
  subgraph RaftRoof["Raft/Roof Microfield"]
    Legumes["Legumes (any bean)\ncontainer planters + trellis"]
    Harvest["Harvest + prep"]
    GofuProc["Gofu processing\n(heat / ferment / sprout + steam)\n→ dry → mill"]
    Pellets["Pellet dough\n(bean meal + binder + optional oil)"]
    DryStore["Dry fully + airtight storage\n(batch ID)"]
    Legumes --> Harvest --> GofuProc --> Pellets --> DryStore
  end

  subgraph Water["Water Loop"]
    Intake["Source water intake\n(salt/brackish)"]
    Pump["Pump + intake screen"]
    Solids["Mechanical solids filter\n(swirl/sock/settle)"]
    Bio["Biofilter media\n(nitrifying bacteria)"]
    Aer["Aeration\n(stone/venturi)"]
    Tank["Fish tank/pen"]
    Return["Return flow"]
    Intake --> Pump --> Solids --> Bio --> Aer --> Tank --> Return --> Tank
  end

  subgraph Knowledge["Knowledge Loop"]
    Daily["Daily log (2 min)\nbehavior, feed, pH, ammonia, nitrite"]
    Weekly["Weekly log (10 min)\ngrowth, mortalities, pellet score, notes"]
    Publish["Publish batches + failures\ncommons iteration"]
    Daily --> Publish
    Weekly --> Publish
  end

  DryStore -->|"Feed (small)\nobserve + remove uneaten"| Tank
  Tank -->|"If cloudy/gasping\nfeed ↓ first"| Daily
