### <a name="aspnet-accessibility-improvement-in-net-471"></a>Verbesserungen der Barrierefreiheit von ASP.NET in .NET Framework 4.7.1

|   |   |
|---|---|
|Details|ASP.NET verbessert die Zusammenarbeit von ASP.NET-Websteuerelementen mit den Funktionen für die Barrierefreiheit in Visual Studio, wodurch ASP.NET-Kunden besser unterstützt werden.  Folgende Änderungen wurden u.a. vorgenommen:<ul><li>Änderungen, durch die fehlende Barrierefreiheitsmuster für Steuerelemente der Benutzeroberfläche implementiert werden. Dazu gehört z.B. das Dialogfeld „Feld hinzufügen“ im Detailansicht-Assistenten.</li><li>Änderungen zur Verbesserung der Anzeige im Modus für hohe Kontraste, z.B. beim DataPager-Feld-Editor.</li><li>Änderungen zur Verbesserung der Tastaturnavigation für Steuerelemente. Dazu gehören z.B. die Fenster „Objektkontext konfigurieren“ oder „Datenquelle konfigurieren“.</li></ul>|
|Vorschlag|**Aktivieren oder Deaktivieren dieser Änderungen:** Damit diese Änderungen in Visual Studio Designer eingesetzt werden können, muss das Tool unter .NET Framework 4.7.1 oder höher ausgeführt werden. Die Webanwendung kann diese Änderungen nutzen, wenn Sie folgende Schritte durchführen:<ul><li>Installieren Sie Visual Studio 2017 15.3 oder höher. Ab dieser Version werden die neuen Barrierefreiheitsfeatures mit der unten aufgeführten AppContext-Option standardmäßig unterstützt.</li><li>Deaktivieren Sie die Legacy-Barrierefreiheitsverhalten, indem Sie in der Konfigurationsdatei „devenv.exe“ dem Abschnitt `<runtime>` die AppContext-Option **Switch.UseLegacyAccessibility** hinzufügen und sie auf `false` festlegen, wie im folgenden Beispiel dargestellt wird.</li></ul><pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;<br />&lt;configuration&gt;<br />&lt;runtime&gt;<br />...</code></pre>|
|Bereich|Gering|
|Version|4.7.1|
|Typ|Neuzuweisung|