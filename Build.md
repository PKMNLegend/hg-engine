arm-none-eabi-as -mthumb -c asm/arm_hooks.s -o build/arm_hooks.o
arm-none-eabi-as -mthumb -c asm/general_hooks.s -o build/general_hooks.o
arm-none-eabi-as -mthumb -c asm/other_hook.s -o build/other_hook.o
arm-none-eabi-as -mthumb -c asm/thumb_help.s -o build/thumb_help.o
arm-none-eabi-ld rom.ld -T src/linker.ld -o build/linked.o build/bag.o build/item.o build/moves.o build/music_tables.o build/npc_trade.o build/overlay.o build/party_menu.o build/pokemon.o build/pokemon_storage_system.o build/repel.o build/save.o build/script_new_cmds.o build/sound.o build/summary.o build/swarms.o build/textbox.o build/trainermoney.o build/arm_hooks.o build/general_hooks.o build/other_hook.o build/thumb_help.o
arm-none-eabi-ld: warning: build/linked.o has a LOAD segment with RWX permissions
arm-none-eabi-objcopy -O binary build/linked.o build/output.bin
arm-none-eabi-as -mthumb -c asm/battle/battle_hooks.s -o build/battle/battle_hooks.o
cp rom.ld rom_gen.ld
. .venv/bin/activate; python3 scripts/generate_ld.py
Generating linker script...
arm-none-eabi-ld rom_gen.ld -T src/battle/linker.ld -o build/battle_linked.o build/battle/ability.o build/battle/ai.o build/battle/anim.o build/battle/battle_calc_damage.o build/battle/battle_controller_player.o build/battle/battle_input.o build/battle/battle_item.o build/battle/battle_pokemon.o build/battle/battle_script_commands.o build/battle/battle_start.o build/battle/mega.o build/battle/other_battle_calculators.o build/battle/weather.o build/battle/battle_hooks.o build/thumb_help.o
arm-none-eabi-ld: warning: build/battle_linked.o has a LOAD segment with RWX permissions
arm-none-eabi-objcopy -O binary build/battle_linked.o build/output_battle.bin
arm-none-eabi-as -mthumb -c asm/field/bdhcam_routine.s -o build/field/bdhcam_routine.o
arm-none-eabi-as -mthumb -c asm/field/field_hooks.s -o build/field/field_hooks.o
arm-none-eabi-ld rom_gen.ld -T src/field/linker.ld -o build/field_linked.o build/field/enemy_party.o build/field/overworld_table.o build/field/pokewalker.o build/field/script_commands.o build/field/bdhcam_routine.o build/field/field_hooks.o build/thumb_help.o
arm-none-eabi-ld: warning: build/field_linked.o has a LOAD segment with RWX permissions
arm-none-eabi-objcopy -O binary build/field_linked.o build/output_field.bin
arm-none-eabi-ld rom_gen.ld -T src/pokedex/linker.ld -o build/pokedex_linked.o build/pokedex/pokedex.o  build/thumb_help.o
arm-none-eabi-ld: warning: build/pokedex_linked.o has a LOAD segment with RWX permissions
arm-none-eabi-objcopy -O binary build/pokedex_linked.o build/output_pokedex.bin
cp rom_gen.ld rom_gen_battle.ld
. .venv/bin/activate; python3 scripts/generate_ld.py rom_gen_battle.ld build/battle_linked.o
Generating linker script...
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/BattleController_BeforeMove.ld -o build/BattleController_BeforeMove_linked.o build/individual/BattleController_BeforeMove.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/BattleController_BeforeMove_linked.o build/output_BattleController_BeforeMove.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/BattleController_MoveEnd.ld -o build/BattleController_MoveEnd_linked.o build/individual/BattleController_MoveEnd.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/BattleController_MoveEnd_linked.o build/output_BattleController_MoveEnd.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/BattleFormChangeCheck.ld -o build/BattleFormChangeCheck_linked.o build/individual/BattleFormChangeCheck.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/BattleFormChangeCheck_linked.o build/output_BattleFormChangeCheck.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/BattleSystem_BufferMessage.ld -o build/BattleSystem_BufferMessage_linked.o build/individual/BattleSystem_BufferMessage.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/BattleSystem_BufferMessage_linked.o build/output_BattleSystem_BufferMessage.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/CalcBaseDamage.ld -o build/CalcBaseDamage_linked.o build/individual/CalcBaseDamage.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/CalcBaseDamage_linked.o build/output_CalcBaseDamage.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/CalculateBallShakes.ld -o build/CalculateBallShakes_linked.o build/individual/CalculateBallShakes.o build/thumb_help.o
arm-none-eabi-ld: warning: build/CalculateBallShakes_linked.o has a LOAD segment with RWX permissions
arm-none-eabi-objcopy -O binary build/CalculateBallShakes_linked.o build/output_CalculateBallShakes.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/CheckDefenderItemEffectOnHit.ld -o build/CheckDefenderItemEffectOnHit_linked.o build/individual/CheckDefenderItemEffectOnHit.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/CheckDefenderItemEffectOnHit_linked.o build/output_CheckDefenderItemEffectOnHit.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/GetMonEvolutionBattle.ld -o build/GetMonEvolutionBattle_linked.o build/individual/GetMonEvolutionBattle.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/GetMonEvolutionBattle_linked.o build/output_GetMonEvolutionBattle.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/GetMonEvolutionInternal.ld -o build/GetMonEvolutionInternal_linked.o build/individual/GetMonEvolutionInternal.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/GetMonEvolutionInternal_linked.o build/output_GetMonEvolutionInternal.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/MoveHitDefenderAbilityCheck.ld -o build/MoveHitDefenderAbilityCheck_linked.o build/individual/MoveHitDefenderAbilityCheck.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/MoveHitDefenderAbilityCheck_linked.o build/output_MoveHitDefenderAbilityCheck.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/ServerBeforeAct.ld -o build/ServerBeforeAct_linked.o build/individual/ServerBeforeAct.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/ServerBeforeAct_linked.o build/output_ServerBeforeAct.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/ServerDoPostMoveEffects.ld -o build/ServerDoPostMoveEffects_linked.o build/individual/ServerDoPostMoveEffects.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/ServerDoPostMoveEffects_linked.o build/output_ServerDoPostMoveEffects.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/ServerFieldConditionCheck.ld -o build/ServerFieldConditionCheck_linked.o build/individual/ServerFieldConditionCheck.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/ServerFieldConditionCheck_linked.o build/output_ServerFieldConditionCheck.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/ServerHPCalc.ld -o build/ServerHPCalc_linked.o build/individual/ServerHPCalc.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/ServerHPCalc_linked.o build/output_ServerHPCalc.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/SwitchInAbilityCheck.ld -o build/SwitchInAbilityCheck_linked.o build/individual/SwitchInAbilityCheck.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/SwitchInAbilityCheck_linked.o build/output_SwitchInAbilityCheck.bin
arm-none-eabi-ld rom_gen_battle.ld -T src/individual/linker/btl_scr_cmd_33_statbuffchange.ld -o build/btl_scr_cmd_33_statbuffchange_linked.o build/individual/btl_scr_cmd_33_statbuffchange.o build/thumb_help.o
arm-none-eabi-objcopy -O binary build/btl_scr_cmd_33_statbuffchange_linked.o build/output_btl_scr_cmd_33_statbuffchange.bin
rm -rf base
###The line below is because of junk files that macOS can create which will interrupt the build process###
find . -name '*.DS_Store' -execdir rm -f {} \;
tools/ndstool -x rom.nds -9 base/arm9.bin -7 base/arm7.bin -y9 base/overarm9.bin -y7 base/overarm7.bin -d base/root -y base/overlay -t base/banner.bin -h base/header.bin
Nintendo DS rom tool 2.1.2 - Mar 24 2025
by Rafael Vuijk, Dave Murphy, Alexei Karpenko
9i (null), 7i (null), unitcode 0
rom.nds Decompression successful!!
. .venv/bin/activate; python3 tools/narcpy.py extract base/root/a/0/2/8 -o build/a028/ -nf
. .venv/bin/activate; python3 scripts/make.py
Decompress arm9.
Inserting code.
/Library/Developer/CommandLineTools/usr/bin/make move_narc
. .venv/bin/activate; python3 tools/narcpy.py extract base/root/a/0/2/7 -o build/text -nf
for file in data/text/010.txt data/text/024.txt data/text/040.txt data/text/197.txt data/text/203.txt data/text/221.txt data/text/222.txt data/text/223.txt data/text/224.txt data/text/300.txt data/text/302.txt data/text/720.txt data/text/721.txt data/text/722.txt data/text/730.txt data/text/731.txt data/text/811.txt build/rawtext/750.txt build/rawtext/751.txt build/rawtext/003.txt build/rawtext/749.txt build/rawtext/237.txt build/rawtext/238.txt build/rawtext/803.txt build/rawtext/812.txt build/rawtext/813.txt build/rawtext/814.txt build/rawtext/815.txt build/rawtext/817.txt build/rawtext/823.txt build/rawtext/729.txt build/rawtext/728.txt; do tools/msgenc -e -c charmap.txt $file build/text/7_$(basename $file .txt); done
. .venv/bin/activate; python3 tools/narcpy.py create build/narc/msg_data.narc build/text -nf
. .venv/bin/activate; python3 tools/narcpy.py extract base/root/a/0/1/2 -o build/a012 -nf
for file in armips/scr_seq/scr_seq_00003_commonscript.s; do tools/armips $file; done
. .venv/bin/activate; python3 tools/narcpy.py create build/narc/scr_seq.narc build/a012 -nf
battle hud layout:
cp build/narc/a007.narc base/root/a/0/0/7
move data:
cp build/narc/a011.narc base/root/a/0/1/1
move particles:
cp build/narc/a029.narc base/root/a/0/2/9
item data files:
cp build/narc/itemdata.narc base/root/a/0/1/7
mon sprite data:
cp build/narc/pokegra.narc base/root/a/0/0/4
cp build/narc/pokegra.narc base/root/pbr/pokegra.narc
opening demo files:
cp build/narc/a262.narc base/root/a/2/6/2
mon data properties:
cp build/narc/mondata.narc base/root/a/0/0/2
sprite offsets:
cp build/narc/spriteoffsets.narc base/root/a/1/8/0
mon height offsets (a005):
cp build/narc/heighttable.narc base/root/a/0/0/5
dex area data:
cp build/narc/dexareas.narc base/root/a/1/3/3
pokedex sort lists:
cp build/narc/a214.narc base/root/a/2/1/4
egg moves:
cp build/narc/kowaza.narc base/root/a/2/2/9
cp build/narc/kowaza.narc base/root/data/kowaza.narc
evolution data:
cp build/narc/a034.narc base/root/a/0/3/4
mon learnset data:
cp build/narc/a033.narc base/root/a/0/3/3
regional dex order:
cp build/narc/a138.narc base/root/a/1/3/8
trainer data:
cp build/narc/a055.narc base/root/a/0/5/5
cp build/narc/a056.narc base/root/a/0/5/6
trainer text:
cp build/narc/trainer_text_map.narc base/root/a/0/5/7
cp build/narc/trainer_text_offsets.narc base/root/a/1/3/1
footprints:
cp build/narc/a069.narc base/root/a/0/6/9
move anims:
cp build/narc/a010.narc base/root/a/0/1/0
move sub animations:
cp build/narc/a061.narc base/root/a/0/6/1
move battle scripts:
cp build/narc/a000.narc base/root/a/0/0/0
move battle scripts:
cp build/narc/a030.narc base/root/a/0/3/0
battle sub effects:
cp build/narc/a001.narc base/root/a/0/0/1
item gfx:
cp build/narc/a018.narc base/root/a/0/1/8
dex gfx for fairy:
cp build/narc/dexgfx.narc base/root/a/0/6/8
battle gfx for fairy:
cp build/narc/battlegfx.narc base/root/a/0/0/8
otherpoke gfx for fairy:
cp build/narc/otherpoke.narc base/root/a/1/1/4
pokemon icons:
tools/armips armips/data/iconpalettetable.s
cp build/narc/pokemonicon.narc base/root/a/0/2/0
wild encounters:
cp build/narc/encounters.narc base/root/a/0/3/7
pokemon overworlds:
cp build/narc/pokemonow.narc base/root/a/0/8/1
pokemon overworld data:
cp build/narc/overworld_properties.narc base/root/a/1/4/1
move an updated gs_sound_data.sdat:
cp build/narc/gs_sound_data.sdat base/root/data/sound/gs_sound_data.sdat
text data:
cp build/narc/msg_data.narc base/root/a/0/2/7
ball spa files:
cp build/narc/ball_spa.narc base/root/a/0/9/5
pokewalker sprites:
cp build/narc/pw_pokegra.narc base/root/a/2/5/6
pokewalker icons:
cp build/narc/pw_pokeicon.narc base/root/a/2/4/8
font:
if [ $(grep -i -c "//#define IMPLEMENT_TRANSPARENT_TEXTBOXES" include/config.h) -eq 0 ]; then cp build/narc/font.narc base/root/a/0/1/6; fi
textbox:
if [ $(grep -i -c "//#define IMPLEMENT_TRANSPARENT_TEXTBOXES" include/config.h) -eq 0 ]; then cp build/narc/textbox.narc base/root/a/0/3/8; fi
scripts:
cp build/narc/scr_seq.narc base/root/a/0/1/2
headbutt trees:
cp build/narc/headbutt.narc base/root/a/2/5/2
trainer gfx:
cp build/narc/trainer_gfx.narc base/root/a/0/5/8
baby mons:
tools/armips armips/data/babymons.s
tutor moves and tm moves:
. .venv/bin/activate; python3 scripts/tm_learnset.py --writetmlist armips/data/tmlearnset.txt
. .venv/bin/activate; python3 scripts/tutor_learnset.py --writemovecostlist armips/data/tutordata.txt
. .venv/bin/activate; python3 scripts/tutor_learnset.py armips/data/tutordata.txt
hidden ability table:
cp build/HiddenAbilityTable.bin build/a028/9_07
base experience table:
cp build/BaseExperienceTable.bin build/a028/9_08
mon overworld data:
tools/armips armips/data/monoverworlds.s
species to ow gfx table:
cp build/SpeciesToOWGfx.bin build/a028/9_10
form data table:
cp build/PokeFormDataTbl.bin build/a028/9_11
form to species mapping table:
cp build/FormToSpeciesMapping.bin build/a028/9_12
form reversion mapping table:
cp build/FormReversionMapping.bin build/a028/9_13
tools/armips armips/global.s
. .venv/bin/activate; python3 tools/narcpy.py create base/root/a/0/2/8 build/a028/ -nf
Making ROM...
tools/ndstool -c test.nds -9 base/arm9.bin -7 base/arm7.bin -y9 base/overarm9.bin -y7 base/overarm7.bin -d base/root -y base/overlay -t base/banner.bin -h base/header.bin
Nintendo DS rom tool 2.1.2 - Mar 24 2025
by Rafael Vuijk, Dave Murphy, Alexei Karpenko
Done.  See output test.nds.