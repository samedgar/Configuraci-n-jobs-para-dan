# Jobs configuration.
#
# Stores information about each job.
#
# NOTE: When having multiple jobs, both jobs will give the income payout to the player
# even if they give the pay for one action (make the configurations with this in mind)
# and each job will get the respective experience.
#
# e.g If player has 2 jobs where job1 gives 10 income and experience for killing a player 
# and job2 gives 5 income and experience for killing a player. When the user kills a player
# they will get 15 income and job1 will gain 10 experience and job2 will gain 5 experience.

Jobs:
  # must be one word
  Lenador:
    # full name of the job (displayed when browsing a job, used when joining and leaving)
    # also can be used as a prefix for the user's name if the option is enabled.
    # Shown as a prefix only when the user has 1 job.
    #
    # NOTE: Must be 1 word
    fullname: Lenador
    # Shortened version of the name of the job. Used as a prefix when the user has more 
    # than 1 job
    shortname: L
    description: Earns money felling and planting trees  
    # The colour of the name, for a full list of supported colours, go to the message config.
    ChatColour: GREEN
    # Option to let you choose what kind of prefix this job adds to your name.
    # options are: full, title, job, shortfull, shorttitle, shortjob and none
    chat-display: full
    # [OPTIONAL] - the maximum level of this class
    #max-level: 100
    # [OPTIONAL] - the maximum number of users on the server that can have this job at 
    # any one time (includes offline players).
    #slots: 1000000
    # Equation used for calculating how much experience is needed to go to the next level.
    # Available parameters:
    #   numjobs - the number of jobs the player has
    #   joblevel - the level the player has attained in the job.
    # NOTE: Please take care of the brackets when modifying this equation.
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    # Equation used for calculating how much income is given per action for the job level.
    # Available parameters:
    #   baseincome - the income for the action at level 1 (as set in the configuration).
    #   joblevel - the level the player has attained in the job.
    # NOTE: Please take care of the brackets when modifying this equation.
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
     # Equation used for calculating how much experience is given per action for the job level.
    # Available parameters:
    #   baseexperience - the experience for the action at level 1 (as set in the configuration).
    #   joblevel - the level the player has attained in the job.
    # NOTE: Please take care of the brackets when modifying this equation.
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    ########################################################################
    # Section used to configure what items the job gets paid for, how much
    # they get paid and how much experience they gain.
    #
    # For break and place, the block name or id is used.
    # You can select a sub-type by using a '-' between the id and the bit
    # value for the sub-type. e.g LOG-0 = usual log, LOG-2 = birch log
    # 17-2 = birch log.
    #
    # If no sub-type is give, the payout will be for all sub-types.
    #
    # To get a list of all available block types, check the
    # bukkit JavaDocs for a complete list of block types
    # http://jd.bukkit.org/apidocs/org/bukkit/Material.html
    # 
    # For kill tags (Kill and custom-kill), the name is the name of the
    # mob.
    # Available mobs:
    #   Chicken
    #   Cow
    #   Pig
    #   Sheep
    #   Wolf
    #   Creeper
    #   Giant
    #   Skeleton
    #   Spider
    #   Zombie
    #   PigZombie
    #   Squid
    #   Ghast
    #   Player
    #   Slime
    #
    # NOTE: mob names are case sensitive.
    #
    # For custom-kill, it is the name of the job (also case sensitive).
    # 
    # NOTE: If a job has both the pay for killing a player and for killing a
    # specific class, they will get both payments.
    ########################################################################
    # payment for breaking a block
    Break:
      # block name/id (with optional sub-type)
      LOG:
        # base income
        income: 5.0
        # base experience
        experience: 5.0
    # payment for placing a block
    Place:
      SAPLING: 
        income: 1.0
        experience: 1.0
      WOOD: 
        income: 2.0
        experience: 2.0
    # killing a mob
  Minero:
    fullname: Minero
    shortname: M
    description: Gana dinero picando minerales y roca.
    ChatColour: DARK_GRAY
    chat-display: full
    #max-level: 100
    #slots: 1000000000000000000
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    Break:
      STONE:
        income: 2.0
        experience: 2.0
      COAL_ORE:
        income: 3.0
        experience: 3.0
      GLOWING_REDSTONE_ORE:
        income: 3.0
        experience: 3.0
      IRON_ORE: 
        income: 4.0
        experience: 4.0
      GOLD_ORE:
        income: 5.0
        experience: 5.0
      LAPIS_ORE:
        income: 5.0
        experience: 5.0
      DIAMOND_ORE:
        income: 6.0
        experience: 6.0
      OBSIDIAN: 
        income: 7.5
        experience: 7.5
      MOSSY_COBBLESTONE:
        income: 6.0
        experience: 6.0
    Place:
      RAILS:
        income: 2.0
        experience: 2.0
      IRON_ORE:
        income: -5.0
        experience: -5.0
      GOLD_ORE:
        income: -6.0
        experience: -6.0      
  Constructor:
    fullname: Constructor
    shortname: C
    description: Gana dinero construyendo.
    ChatColour: WHITE
    chat-display: full
    #max-level: 100
    #slots: 100000000000000
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    Place:
      COBBLESTONE:
        income: 1.0
        experience: 1.0
      WOOD:
        income: 1.5
        experience: 1.5
      FENCE:
        income: 1.5
        experience: 1.5
      WOOL:
        income: 1.5
        experience: 1.5
      STONE:
        income: 2.25
        experience: 2.25
      GLOWSTONE:
        income: 3.0
        experience: 3.0
      SANDSTONE:
        income: 2.0
        experience: 2.0
      GLASS:
        income: 3.0
        experience: 3.0
      BRICK:
        income: 4.0
        experience: 4.0
      LAPIS_BLOCK:
        income: 5.0
        experience: 5.0
      DOUBLE_STEP:
        income: 2.0
        experience: 2.0
      STEP:
        income: 2.0
        experience: 2.0
      BOOKSHELF:
        income: 3.0
        experience: 3.0
      WOOD_STAIRS:
        income: 2.0
        experience: 2.0
      COBBLESTONE_STAIRS:
        income: 2.0
        experience: 2.0
      MOSSY_COBBLESTONE:
        income: 5.0
        experience: 5.0
      DIAMOND_BLOCK:
        income: 5.0
        experience: 5.0
      GOLD_BLOCK:
        income: 5.0
        experience: 5.0     
  Granjero:
    fullname: Granjero
    shortname: Gr
    description: Gana dinero cultivando.
    ChatColour: BLUE
    chat-display: full
    #max-level: 100
    #slots: 1000000000000
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    Break:
      CROPS-7:
        income: 4.0
        experience: 4.0
      SUGAR_CANE_BLOCK:
        income: 4.0
        experience: 4.0
    Place:
      CROPS-0:
        income: 3.0
        experience: 3.0
      SUGAR_CANE_BLOCK:
        income: 1.0
        experience: 1.0     
  Cazador:
    fullname: Cazador
    shortname: Ca
    description: Gana dinero matando mobs.
    ChatColour: RED
    chat-display: full
    #max-level: 100
    #slots: 1000000000
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    Kill:
      Chicken:
        income: 2.5
        experience: 2.5
      Cow:
        income: 2.5
        experience: 2.5
      Pig:
        income: 2.5
        experience: 2.5
      Sheep: 
        income: 2.5
        experience: 2.5
      Wolf: 
        income: 5.0
        experience: 5.0
      Creeper: 
        income: 10.0
        experience: 10.0
      Skeleton: 
        income: 10.0
        experience: 10.0
      Spider:
        income: 10.0
        experience: 10.0
      Zombie: 
        income: 10.0
        experience: 10.0
  Pescador:
    fullname: Pescador
    shortname: Pe
    description: Gana dinero pescando.
    ChatColour: AQUA
    chat-display: full
    #max-level: 100
    #slots: 10000000
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    Fish:
      RAW_FISH:
        income: 4.0
        experience: 4.0
  Herrero_De_Espadas:
    fullname: Herrero_De_Espadas
    shortname: Hs
    description: Gana dinero haciendo espadas.
    ChatColour: DARK_PURPLE
    chat-display: full
    #max-level: 100
    #slots: 100000000000
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    Craft:
      WOOD_SWORD:
        income: 1.0
        experience: 1.0
      IRON_SWORD:
        income: 2.0
        experience: 2.0
      GOLD_SWORD:
        income: 3.0
        experience: 3.0
      DIAMOND_SWORD:
        income: 4.0
        experience: 4.0
    Repair:
      WOOD_SWORD:
        income: 1.0
        experience: 1.0
      IRON_SWORD:
        income: 2.0
        experience: 2.0
      GOLD_SWORD:
        income: 3.0
        experience: 3.0
      DIAMOND_SWORD:
        income: 4.0
        experience: 4.0
    Smelt:
      IRON_INGOT:
        income: 2.0
        experience: 2.0
      GOLD_INGOT:
        income: 2.0
        experience: 2.0
  Alquimista:
    fullname: Alquimista
    shortname: Al
    description: Gana dinero haciendo pociones.
    ChatColour: LIGHT_PURPLE
    chat-display: full
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    Brew:
      NETHER_STALK:
        income: 1.0
        experience: 1.0
      REDSTONE:
        income: 2.0
        experience: 2.0
      GLOWSTONE_DUST:
        income: 2.0
        experience: 2.0
      SPIDER_EYE:
        income: 2.0
        experience: 2.0
      FERMENTED_SPIDER_EYE:
        income: 2.0
        experience: 2.0
      BLAZE_POWDER:
        income: 2.0
        experience: 2.0
      SUGAR:
        income: 2.0
        experience: 2.0
      SPECKLED_MELON:
        income: 4.0
        experience: 4.0
      MAGMA_CREAM:
        income: 4.0
        experience: 4.0
      GHAST_TEAR:
        income: 4.0
        experience: 4.0
  Encantador:
    fullname: Encantador
    shortname: E
    description: Gana dinero encantando espadas.
    ChatColour: DARK_BLUE
    chat-display: full
    #max-level: 100
    #slots: 100000000000
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
    Enchant:
      WOOD_SWORD:
        income: 4.0
        experience: 4.0
      IRON_SWORD:
        income: 6.0
        experience: 6.0
      GOLD_SWORD:
        income: 8.0
        experience: 8.0
      DIAMOND_SWORD:
        income: 10.0
        experience: 10.0
  None:
    fullname: None
    shortname: N
    ChatColour: WHITE
    chat-display: none
    #max-level: 10
    #slots: 10
    leveling-progression-equation: 100*((1.13+(0.01*(numjobs-1)))^(joblevel-1))
    income-progression-equation: baseincome*((1.05)^(joblevel-1))
    experience-progression-equation: baseexperience*((1.05)^(joblevel-1))
