


## LookAndFeel Bug WorkAround

TODO : Mettre en forme synthétique https://github.com/MarginallyClever/Makelangelo-software/issues/365#issuecomment-996154780

https://docs.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html


KO : java -Dswing.defaultlaf=com.sun.java.swing.plaf.gtk.GTKLookAndFeel -jar Makelangelo-7.28.2-with-dependencies.jar 
(car c'est le -Dswing.systemlaf qu'il faut changer et que com.sun.java.swing.plaf.gtk.GTKLookAndFeel pose problème :) )

### Solution 

java -Dswing.systemlaf=javax.swing.pl.metal.MetalLookAndFeel -jar Makelangelo-7.28.2-with-dependencies.jar

Edit : 20/12/2021
A etait resolut 
par le commit 
[a83707433afa26baf691731d674411b0ec5f7a37](https://github.com/MarginallyClever/Makelangelo-software/commit/a83707433afa26baf691731d674411b0ec5f7a37)
donc dans la nightly [makelangelo-nightly-20211220-a83707.jar](https://github.com/MarginallyClever/Makelangelo-software/releases/download/Nightly/makelangelo-nightly-20211220-a83707.jar)
 et ne devrais plus poser problèmes dans la prochaine release.



### BUG ?

```
java --version
```
```
java 17 2021-09-14 LTS
Java(TM) SE Runtime Environment (build 17+35-LTS-2724)
Java HotSpot(TM) 64-Bit Server VM (build 17+35-LTS-2724, mixed mode, sharing)
```

```
~/Downloads/Makelangelo-7.28.2$ java -jar Makelangelo-7.28.2-with-dependencies.jar 
```
Si je clic sur la bar des menu "File" -> " Prefrences" ou sur "Paper" -> "OpenSettings" pas de nouvelle fenetre et une belle erreur

```
Exception in thread "AWT-EventQueue-0" java.lang.NullPointerException: Cannot invoke "java.util.ArrayList.add(Object)" because "this.propertyChangeListeners" is null
	at com.marginallyclever.makelangelo.select.SelectPanel.addPropertyChangeListener(SelectPanel.java:71)
	at java.desktop/javax.swing.plaf.synth.SynthPanelUI.installListeners(SynthPanelUI.java:89)
	at java.desktop/javax.swing.plaf.synth.SynthPanelUI.installUI(SynthPanelUI.java:69)
	at java.desktop/javax.swing.JComponent.setUI(JComponent.java:730)
	at java.desktop/javax.swing.JPanel.setUI(JPanel.java:153)
	at java.desktop/javax.swing.JPanel.updateUI(JPanel.java:129)
	at java.desktop/javax.swing.JPanel.<init>(JPanel.java:89)
	at java.desktop/javax.swing.JPanel.<init>(JPanel.java:112)
	at java.desktop/javax.swing.JPanel.<init>(JPanel.java:120)
	at com.marginallyclever.makelangelo.select.SelectPanel.<init>(SelectPanel.java:32)
	at com.marginallyclever.makelangelo.paper.PaperSettings.<init>(PaperSettings.java:61)
	at com.marginallyclever.makelangelo.Makelangelo.openPaperSettings(Makelangelo.java:217)
	at com.marginallyclever.makelangelo.Makelangelo.lambda$2(Makelangelo.java:210)
	at java.desktop/javax.swing.AbstractButton.fireActionPerformed(AbstractButton.java:1972)
	at java.desktop/javax.swing.AbstractButton$Handler.actionPerformed(AbstractButton.java:2313)
	at java.desktop/javax.swing.DefaultButtonModel.fireActionPerformed(DefaultButtonModel.java:405)
	at java.desktop/javax.swing.DefaultButtonModel.setPressed(DefaultButtonModel.java:262)
	at java.desktop/javax.swing.AbstractButton.doClick(AbstractButton.java:374)
	at java.desktop/javax.swing.plaf.basic.BasicMenuItemUI.doClick(BasicMenuItemUI.java:1028)
	at java.desktop/javax.swing.plaf.basic.BasicMenuItemUI$Handler.mouseReleased(BasicMenuItemUI.java:1072)
	at java.desktop/java.awt.Component.processMouseEvent(Component.java:6626)
	at java.desktop/javax.swing.JComponent.processMouseEvent(JComponent.java:3389)
	at java.desktop/java.awt.Component.processEvent(Component.java:6391)
	at java.desktop/java.awt.Container.processEvent(Container.java:2266)
	at java.desktop/java.awt.Component.dispatchEventImpl(Component.java:5001)
	at java.desktop/java.awt.Container.dispatchEventImpl(Container.java:2324)
	at java.desktop/java.awt.Component.dispatchEvent(Component.java:4833)
	at java.desktop/java.awt.LightweightDispatcher.retargetMouseEvent(Container.java:4948)
	at java.desktop/java.awt.LightweightDispatcher.processMouseEvent(Container.java:4575)
	at java.desktop/java.awt.LightweightDispatcher.dispatchEvent(Container.java:4516)
	at java.desktop/java.awt.Container.dispatchEventImpl(Container.java:2310)
	at java.desktop/java.awt.Window.dispatchEventImpl(Window.java:2780)
	at java.desktop/java.awt.Component.dispatchEvent(Component.java:4833)
	at java.desktop/java.awt.EventQueue.dispatchEventImpl(EventQueue.java:773)
	at java.desktop/java.awt.EventQueue$4.run(EventQueue.java:722)
	at java.desktop/java.awt.EventQueue$4.run(EventQueue.java:716)
	at java.base/java.security.AccessController.doPrivileged(AccessController.java:399)
	at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(ProtectionDomain.java:86)
	at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(ProtectionDomain.java:97)
	at java.desktop/java.awt.EventQueue$5.run(EventQueue.java:746)
	at java.desktop/java.awt.EventQueue$5.run(EventQueue.java:744)
	at java.base/java.security.AccessController.doPrivileged(AccessController.java:399)
	at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(ProtectionDomain.java:86)
	at java.desktop/java.awt.EventQueue.dispatchEvent(EventQueue.java:743)
	at java.desktop/java.awt.EventDispatchThread.pumpOneEventForFilters(EventDispatchThread.java:203)
	at java.desktop/java.awt.EventDispatchThread.pumpEventsForFilter(EventDispatchThread.java:124)
	at java.desktop/java.awt.EventDispatchThread.pumpEventsForHierarchy(EventDispatchThread.java:113)
	at java.desktop/java.awt.EventDispatchThread.pumpEvents(EventDispatchThread.java:109)
	at java.desktop/java.awt.EventDispatchThread.pumpEvents(EventDispatchThread.java:101)
	at java.desktop/java.awt.EventDispatchThread.run(EventDispatchThread.java:90)
```

If i comment in the source code :
https://github.com/MarginallyClever/Makelangelo-software/blob/cb56084ab3ba7aa7b9c0ff6e57b1a1707aa6ed49/src/main/com/marginallyclever/makelangelo/Makelangelo.java#L787
or 
https://github.com/MarginallyClever/Makelangelo-software/blob/cb56084ab3ba7aa7b9c0ff6e57b1a1707aa6ed49/src/main/com/marginallyclever/makelangelo/Makelangelo.java#L170
and run it under NetBeans no more exceptions and the new JFrame "PaperSettings" show.

### Analyse 

strangely in my System / Java environment it seems that this method (an Override of PropertyChangeListener that this class implements) :

https://github.com/MarginallyClever/Makelangelo-software/blob/cb56084ab3ba7aa7b9c0ff6e57b1a1707aa6ed49/src/main/com/marginallyclever/makelangelo/select/SelectPanel.java#L70-L72

happens to be called before the instantiation of the class "SelectPanel" and therefore "propertyChangeListeners"  is null :

https://github.com/MarginallyClever/Makelangelo-software/blob/cb56084ab3ba7aa7b9c0ff6e57b1a1707aa6ed49/src/main/com/marginallyclever/makelangelo/select/SelectPanel.java#L68


 maybe adding a "if ( propertyChangeListeners != null )" ... ? 

Sinon en contournement changer de LookAndFeel.

```
    void LookAndFeelDebug() {

        System.out.printf("DEBUG : %50s =  %s\n", "UIManager.getSystemLookAndFeelClassName()", UIManager.getSystemLookAndFeelClassName());
        System.out.printf("DEBUG : %50s =  %s\n", "UIManager.getLookAndFeel().getClass().getName()", UIManager.getLookAndFeel().getClass().getName());
        System.out.printf("DEBUG : %50s =  %s\n", "UIManager.getCrossPlatformLookAndFeelClassName()", UIManager.getCrossPlatformLookAndFeelClassName());
        System.out.println();
        // list all InstalledLookAndFeels()
        UIManager.LookAndFeelInfo[] lafInfo = UIManager.getInstalledLookAndFeels();
        for (UIManager.LookAndFeelInfo lafi : lafInfo) {
            System.out.println(lafi.getClassName());
        }
    }
```            
```
DEBUG : UIManager.getSystemLookAndFeelClassName()            =  com.sun.java.swing.plaf.gtk.GTKLookAndFeel
DEBUG : UIManager.getLookAndFeel().getClass().getName()      =  javax.swing.plaf.nimbus.NimbusLookAndFeel
DEBUG : UIManager.getCrossPlatformLookAndFeelClassName()     =  javax.swing.plaf.metal.MetalLookAndFeel

javax.swing.plaf.metal.MetalLookAndFeel
javax.swing.plaf.nimbus.NimbusLookAndFeel
com.sun.java.swing.plaf.motif.MotifLookAndFeel
com.sun.java.swing.plaf.gtk.GTKLookAndFeel
```

```
java -jar Makelangelo-7.30.2-with-dependencies.jar
java -Dswing.systemlaf=javax.swing.plaf.metal.MetalLookAndFeel -jar Makelangelo-7.30.2-with-dependencies.jar
java -Dswing.systemlaf=javax.swing.plaf.nimbus.NimbusLookAndFeel -jar Makelangelo-7.30.2-with-dependencies.jar
java -Dswing.systemlaf=com.sun.java.swing.plaf.motif.MotifLookAndFeel -jar Makelangelo-7.30.2-with-dependencies.jar
java -Dswing.systemlaf=com.sun.java.swing.plaf.gtk.GTKLookAndFeel -jar Makelangelo-7.30.2-with-dependencies.jar
```



## Là c'est .... car j'ai joué en mode dev a créer un fichier de traduction et la version 7.28.2 ne là pas ...

### Solution 
Effacer le fichier de config qui spécifie d'utiliser un fichier de langue qui n'existe pas pour cette version
```
rm ~/.java/.userPrefs/DrawBot/Language/prefs.xml 
```
```
java -jar ./Makelangelo-7.28.2-with-dependencies.jar 
log dir=/home/q6/Downloads/i_polar/Makelangelo-7.28.2/
déc. 17, 2021 3:20:00 AM java.util.prefs.FileSystemPreferences$6 run
WARNING: Prefs file removed in background /home/q6/.java/.userPrefs/DrawBot/Language/prefs.xml
```

ou le remettre a sa valeur par defaut 
```
cat ~/.java/.userPrefs/DrawBot/Language/prefs.xml 
```
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map SYSTEM "http://java.sun.com/dtd/preferences.dtd">
<map MAP_XML_VERSION="1.0">
<entry key="language" value="English"/>
</map>
```

### Problème
java -Dswing.defaultlaf=com.sun.java.swing.plaf.gtk.GTKLookAndFeel -jar Makelangelo-7.28.2-with-dependencies.jar 
ou 
java -jar ./Makelangelo-7.28.2-with-dependencies.jar 

Juste le splash screen qui saffiche sans disparaitre et si en console texte on a :

```
log dir=/home/q6/Downloads/Makelangelo-7.28.2/
Exception in thread "AWT-EventQueue-0" java.lang.ExceptionInInitializerError
	at com.marginallyclever.makelangelo.SaveDialog.<init>(SaveDialog.java:19)
	at com.marginallyclever.makelangelo.Makelangelo.<init>(Makelangelo.java:134)
	at com.marginallyclever.makelangelo.Makelangelo.lambda$29(Makelangelo.java:774)
	at java.desktop/java.awt.event.InvocationEvent.dispatch(InvocationEvent.java:318)
	at java.desktop/java.awt.EventQueue.dispatchEventImpl(EventQueue.java:771)
	at java.desktop/java.awt.EventQueue$4.run(EventQueue.java:722)
	at java.desktop/java.awt.EventQueue$4.run(EventQueue.java:716)
	at java.base/java.security.AccessController.doPrivileged(AccessController.java:399)
	at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(ProtectionDomain.java:86)
	at java.desktop/java.awt.EventQueue.dispatchEvent(EventQueue.java:741)
	at java.desktop/java.awt.EventDispatchThread.pumpOneEventForFilters(EventDispatchThread.java:203)
	at java.desktop/java.awt.EventDispatchThread.pumpEventsForFilter(EventDispatchThread.java:124)
	at java.desktop/java.awt.EventDispatchThread.pumpEventsForHierarchy(EventDispatchThread.java:113)
	at java.desktop/java.awt.EventDispatchThread.pumpEvents(EventDispatchThread.java:109)
	at java.desktop/java.awt.EventDispatchThread.pumpEvents(EventDispatchThread.java:101)
	at java.desktop/java.awt.EventDispatchThread.run(EventDispatchThread.java:90)
Caused by: java.lang.NullPointerException: Cannot invoke "com.marginallyclever.makelangelo.TranslatorLanguage.get(String)" because the return value of "java.util.Map.get(Object)" is null
	at com.marginallyclever.makelangelo.Translator.get(Translator.java:215)
	at com.marginallyclever.makelangelo.makeArt.io.vector.LoadScratch3.<init>(LoadScratch3.java:68)
	at com.marginallyclever.makelangelo.makeArt.io.vector.TurtleFactory.<clinit>(TurtleFactory.java:17)
	... 16 more


```

```
cat ~/.java/.userPrefs/DrawBot/Language/prefs.xml 
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map SYSTEM "http://java.sun.com/dtd/preferences.dtd">
<map MAP_XML_VERSION="1.0">
<entry key="language" value="Français"/>
</map>
```
