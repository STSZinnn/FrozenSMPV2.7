FROST PLUGIN v2.7 - Paper 1.21.11 / Java 21

GitHub build instructions:
1. Upload/update src/, build.gradle.kts, settings.gradle.kts in your
   existing GitHub repository. The .github workflow is already in the ZIP.
2. Keep or create .github/workflows/build.yml using the provided YAML.
3. GitHub > Actions > Build Frost Plugin > Run workflow.
4. Download the Frost-Plugin artifact and extract the JAR.
5. Stop your server, remove the old PunchSnowball JAR, add the new JAR to
   plugins/, and restart. Keep plugins/PunchSnowball/trusted.yml.
6. Use /frost as OP to get FRESH items containing the new enchantments.
7. /frost config controls cooldowns, crossbow, armor, and effect strengths.

Minecraft technical notes:
- Unsafe enchantments (e.g. Looting on bows, Lunge V beyond vanilla cap)
  are stored as real enchantments, but unsupported effects may be cosmetic.
- Crossbow Infinity is nonfunctional in vanilla; this plugin prevents ammo
  consumption on loading with EntityLoadCrossbowEvent, but players must
  have at least one Arrow in inventory. Menu gives one if missing.
- Armor potion buffs are refreshed every second and fade shortly after
  removal. The helmet highlights other players within 15 blocks for 10s.
- TNT damage radius changed to 2 blocks with a 30-tick (1.5s) fuse.
- Flame burning is four 1-HP damage pulses at 1s intervals, negated by
  Fire Resistance, on top of the existing initial lava wave's damage.
- The Warden Shriek ability's chosen default cooldown is 40 seconds.
- Configuration changes use /frost reload, or edit with /frost config.

IMPORTANT: This package includes source, NOT a compiled JAR. Build/test in
GitHub Actions. Back up your server before updating. No resource pack or
custom item model is added in this version.
