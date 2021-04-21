# == Minecraft Trolling Features ==

These troll functions are from the plugins: **ContraPloit**, **ProPloit**, **CashPloit3**

Have fun

---------------------------------

<br>

## || Packets ||
<br>


**-- Demoscreen --**

1.8.8:
```java
(((CraftPlayer)p).getHandle()).playerConnection.sendPacket((Packet)new PacketPlayOutGameStateChange(5, 0.0F));
```

1.16: 
```java
(((CraftPlayer)p).getHandle()).playerConnection.sendPacket(new PacketPlayOutGameStateChange(new PacketPlayOutGameStateChange.a(5),0.0F));
```
<br>
<br>

**-- Endscreen / WorldLoading Screen --**

1.8.8:
```java
(((CraftPlayer)p).getHandle()).playerConnection.sendPacket((Packet)new PacketPlayOutGameStateChange(4, 0.0F));
```

1.16:
```java
(((CraftPlayer)p).getHandle()).playerConnection.sendPacket(new PacketPlayOutGameStateChange(new PacketPlayOutGameStateChange.a(4),0.0F));
```
<br>
<br>

**-- Change Contrast --**

1.8.8:
```java
(((CraftPlayer)p).getHandle()).playerConnection.sendPacket((Packet)new PacketPlayOutGameStateChange(7, 14.0F));
```

1.16:
```java
(((CraftPlayer)p).getHandle()).playerConnection.sendPacket(new PacketPlayOutGameStateChange(new PacketPlayOutGameStateChange.a(7),14.0F));
```
<br>
<br>

**-- Blackscreen --**

1.8.8:
```java
(((CraftPlayer)p).getHandle()).playerConnection.sendPacket((Packet)new PacketPlayOutGameStateChange(7, 5.0F));
```
<br>

1.16:
**NOT WORKING**
<br>
<br>

**-- LSD Troll --**

1.16:
```java
Bukkit.getScheduler().scheduleSyncRepeatingTask(Main.instance, new Runnable()
	    {
	        public void run() {
	        	p.playSound(p.getLocation(), Sound.ENTITY_BAT_HURT, 50.0f, 1.5f);
	        	p.playSound(p.getLocation(), Sound.BLOCK_NOTE_BLOCK_BASS, 50.0f, 1.0f);
	        	
	        	(((CraftPlayer)p).getHandle()).playerConnection.sendPacket(new PacketPlayOutGameStateChange(new PacketPlayOutGameStateChange.a(7),14.0F));
	        	Bukkit.getServer().getScheduler().scheduleSyncDelayedTask((Plugin) Main.instance, () -> (((CraftPlayer)p).getHandle()).playerConnection.sendPacket(new PacketPlayOutGameStateChange(new PacketPlayOutGameStateChange.a(7),10.0F)), 2L);

	        	Bukkit.getServer().getScheduler().scheduleSyncDelayedTask((Plugin) Main.instance, () -> (((CraftPlayer)p).getHandle()).playerConnection.sendPacket(new PacketPlayOutGameStateChange(new PacketPlayOutGameStateChange.a(7),17.0F)), 3L);

	        	Bukkit.getServer().getScheduler().scheduleSyncDelayedTask((Plugin) Main.instance, () -> (((CraftPlayer)p).getHandle()).playerConnection.sendPacket(new PacketPlayOutGameStateChange(new PacketPlayOutGameStateChange.a(7),7.0F)), 4L);


	        	Location tp = p.getLocation();
	        	tp.setPitch(-90);
	        	p.teleport(tp);
	        	
	        	p.closeInventory();
	        	p.getInventory().clear();

	        }
	    }, 1L, 2L);
```
<br>

---------------------------------

<br>

## || ClientSide Trolling ||
<br>


**-- All Blocks replacing with TNT (ca. 100 Blocks) --**

1.8.8:
```java
for (double x = p.getLocation().getX() - 10; x <= p.getLocation().getX() + 100; x++) {
			for (double y = p.getLocation().getY() - 10; y <= p.getLocation().getY() + 100; y++) {
				for (double z = p.getLocation().getZ() - 10; z <= p.getLocation().getZ() + 100; z++) {
					Location l = new Location(p.getWorld(), x, y, z);
					if (l.getBlock().getType().getId() != 0) {
						p.sendBlockChange(l, 46, (byte)0);
					}
				
				}
			}
				
		}
```

1.16:
```java
for (double x = p.getLocation().getX() - 10; x <= p.getLocation().getX() + 100; x++) {
			for (double y = p.getLocation().getY() - 10; y <= p.getLocation().getY() + 100; y++) {
				for (double z = p.getLocation().getZ() - 10; z <= p.getLocation().getZ() + 100; z++) {
					Location l = new Location(p.getWorld(), x, y, z);
					if (l.getBlock().getType() != Material.AIR) {
						p.sendBlockChange(l, Material.TNT, (byte) 0);
					}
				
				}
			}
				
		}
```
<br>
<br>

**-- Spawn over Player a ClientSide Pen!s --**

1.8.8:
```java
for (double x = p.getLocation().getX() - 4; x <= p.getLocation().getX() + 4; x++) {
			for (double y = p.getLocation().getY() + 4; y <= p.getLocation().getY() + 6; y++) {
				for (double z = p.getLocation().getZ(); z <= p.getLocation().getZ() + 2; z++) {
					
					p.sendBlockChange(new Location(p.getWorld(),x,y,z), Material.WOOL, (byte) 6);
					
				}
			}
		
		}
		
		for (double x = p.getLocation().getX() - 1; x <= p.getLocation().getX() + 1; x++) {
			for (double y = p.getLocation().getY() + 6; y <= p.getLocation().getY() + 12; y++) {
				for (double z = p.getLocation().getZ(); z <= p.getLocation().getZ() + 2; z++) {
					
					p.sendBlockChange(new Location(p.getWorld(),x,y,z), Material.WOOL, (byte) 6);
					
				}
			}
		
		}
		
		for (double x = p.getLocation().getX() - 1; x <= p.getLocation().getX() + 1; x++) {
			for (double y = p.getLocation().getY() + 12; y <= p.getLocation().getY() + 14; y++) {
				for (double z = p.getLocation().getZ(); z <= p.getLocation().getZ() + 2; z++) {
					
					p.sendBlockChange(new Location(p.getWorld(),x,y,z), Material.WOOL, (byte) 2);
					
				}
			}
		
		}
```

1.16:
```java
for (double x = p.getLocation().getX() - 4; x <= p.getLocation().getX() + 4; x++) {
			for (double y = p.getLocation().getY() + 4; y <= p.getLocation().getY() + 6; y++) {
				for (double z = p.getLocation().getZ(); z <= p.getLocation().getZ() + 2; z++) {
					
					p.sendBlockChange(new Location(p.getWorld(),x,y,z), Material.PINK_WOOL, (byte) 6);
					
				}
			}
		
		}
		
		for (double x = p.getLocation().getX() - 1; x <= p.getLocation().getX() + 1; x++) {
			for (double y = p.getLocation().getY() + 6; y <= p.getLocation().getY() + 12; y++) {
				for (double z = p.getLocation().getZ(); z <= p.getLocation().getZ() + 2; z++) {
					
					p.sendBlockChange(new Location(p.getWorld(),x,y,z), Material.PINK_WOOL, (byte) 6);
					
				}
			}
		
		}
		
		for (double x = p.getLocation().getX() - 1; x <= p.getLocation().getX() + 1; x++) {
			for (double y = p.getLocation().getY() + 12; y <= p.getLocation().getY() + 14; y++) {
				for (double z = p.getLocation().getZ(); z <= p.getLocation().getZ() + 2; z++) {
					
					p.sendBlockChange(new Location(p.getWorld(),x,y,z), Material.MAGENTA_WOOL, (byte) 2);
					
				}
			}
		
		}
```

<br>

---------------------------------

<br>

## || Other Trolls ||
<br>


**-- Piss rocket --**

1.8.8:
```java
p.setVelocity(new Vector(0,0.5,0));

Bukkit.getScheduler().scheduleSyncRepeatingTask(Main.instance, new Runnable()
	    {
	        public void run() {

				p.setVelocity(new Vector(0,0.3,0));
				p.getWorld().playSound(p.getLocation(), Sound.FIZZ, 5.0f, 5.0f);
				p.getWorld().spawnFallingBlock(p.getLocation(), Material.WOOL, (byte) 4);

	        }
	    }, 1L, 2L);
```

1.16:
```java
p.setVelocity(new Vector(0,0.5,0));

Bukkit.getScheduler().scheduleSyncRepeatingTask(Main.instance, new Runnable()
	    {
	        public void run() {

				p.setVelocity(new Vector(0,0.3,0));
				p.getWorld().spawnFallingBlock(p.getLocation(), Material.YELLOW_WOOL, (byte) 0);

	        }
	    }, 1L, 2L);
```
<br>
<br>

**-- Beyblade --**

1.8.8 + 1.16:
```java
Bukkit.getScheduler().scheduleSyncRepeatingTask(Main.instance, new Runnable()
	    {
	        public void run() {

				Location tp = p.getLocation();
				tp.setYaw(tp.getYaw() + 2);
				p.teleport(tp);
				p.teleport(tp);

	        }
	    }, 1L, 2L);
```
<br>
<br>

**-- Virus Simulation --**

1.8.8:
```java
final Timer timer = new Timer();
          timer.scheduleAtFixedRate(new TimerTask() {
              int i = Integer.parseInt("" + 1);
			public void run() {
              	v.sendTitle("§a" + i++ + "%", "§eVirus_zSu934394Jd.exe §cwird runtergeladen");
              	v.playSound(v.getLocation(), Sound.NOTE_BASS, 1.0f, 50.0f);
                  if (i> 100) {
                      timer.cancel();
                      v.getWorld().strikeLightning(v.getLocation());
                      v.kickPlayer("§fStack Trace:\njava.lang.ArrayIndexOutOfBoundsException: 3\n"
                      		+ "  at java.common.WindowsVirus.execute(Infected.java:17)\n"
                      		+ "  at java.common.Encrypter.main(Infected.java:11)");
              }
              }
          }, 0, 300);
```

1.16:
```java
final Timer timer = new Timer();
          timer.scheduleAtFixedRate(new TimerTask() {
              int i = Integer.parseInt("" + 1);
			public void run() {
              	v.sendTitle("§a" + i++ + "%", "§eVirus_zSu934394Jd.exe §cwird runtergeladen");
              	v.playSound(v.getLocation(), Sound.BLOCK_NOTE_BLOCK_BASS, 1.0f, 50.0f);
                  if (i> 100) {
                      timer.cancel();
                      v.getWorld().strikeLightning(v.getLocation());
                      Bukkit.getScheduler().runTask(Start.instance, () -> v.kickPlayer("§fStack Trace:\njava.lang.ArrayIndexOutOfBoundsException: 3\n"
                        		+ "  at java.common.WindowsVirus.execute(Infected.java:17)\n"
                          		+ "  at java.common.Encrypter.main(Infected.java:11)"));
              }
              }
          }, 0, 300);
```
<br>
<br>

**-- Virus Simulation --**

1.8.8:
```java
final Timer timer = new Timer();
          timer.scheduleAtFixedRate(new TimerTask() {
              int i = Integer.parseInt("" + 1);
			public void run() {
              	v.sendTitle("§a" + i++ + "%", "§eVirus_zSu934394Jd.exe §cwird runtergeladen");
              	v.playSound(v.getLocation(), Sound.NOTE_BASS, 1.0f, 50.0f);
                  if (i> 100) {
                      timer.cancel();
                      v.getWorld().strikeLightning(v.getLocation());
                      v.kickPlayer("§fStack Trace:\njava.lang.ArrayIndexOutOfBoundsException: 3\n"
                      		+ "  at java.common.WindowsVirus.execute(Infected.java:17)\n"
                      		+ "  at java.common.Encrypter.main(Infected.java:11)");
              }
              }
          }, 0, 300);
```

1.16:
```java
final Timer timer = new Timer();
          timer.scheduleAtFixedRate(new TimerTask() {
              int i = Integer.parseInt("" + 1);
			public void run() {
              	v.sendTitle("§a" + i++ + "%", "§eVirus_zSu934394Jd.exe §cwird runtergeladen");
              	v.playSound(v.getLocation(), Sound.BLOCK_NOTE_BLOCK_BASS, 1.0f, 50.0f);
                  if (i> 100) {
                      timer.cancel();
                      v.getWorld().strikeLightning(v.getLocation());
                      Bukkit.getScheduler().runTask(Start.instance, () -> v.kickPlayer("§fStack Trace:\njava.lang.ArrayIndexOutOfBoundsException: 3\n"
                        		+ "  at java.common.WindowsVirus.execute(Infected.java:17)\n"
                          		+ "  at java.common.Encrypter.main(Infected.java:11)"));
              }
              }
          }, 0, 300);
```

<br>

---------------------------------

<br>
