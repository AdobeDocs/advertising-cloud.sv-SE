---
title: Enhetsoberoende lösningar
description: Läs mer om funktioner för olika enheter.
feature: DSP Introduction
exl-id: 29f8ec41-35a6-4a29-a638-82a2929a8fe6
source-git-commit: d10e1c24ee7c93eaab3fd4fefe853860226cc8e2
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 0%

---

# Enhetsoberoende lösningar

Tack vare Advertising Cloud DSP-integreringar med [!DNL LiveRamp] och [!DNL Adobe Device Co-op] kan ni utöka er målgrupp till alla kända enheter, inte bara de enheter varumärket har spårat. Integreringarna ger även frekvensbegränsning och attribueringsmätning på alla enheter.

När du använder ett personbaserat enhetsdiagram som stöds kan du:

* Matcha målgrupper över alla kanaler och enheter för att leverera annonser till människor och hushåll, i stället för till enheter.
* Balansera annonsexponering genom förståelse och frekvens mellan olika individer.
* Testa strategier som visar och konverterar målgrupper över olika kanaler och enheter.

## Fördelar med varje enhetsdiagram

* [!DNL Adobe Device Co-op]:
   * Tillhandahåller en pool med deltagande Adobe-annonsörer för deterministiska och sannolika uppgifter
   * Ger starka cookie ID-anslutningar som drivs av webbesökare på datorer och mobila enheter
   * Inkluderar data främst från USA och Kanada
   * Har inga användningsavgifter

* [!DNL LiveRamp] enhetsdiagram:
   * Tillhandahåller en deterministisk datapool, inklusive kunddata offline
   * Gäller även cookie-ID:n och mobila enhets-ID:n
   * Inkluderar data främst från USA
   * Är kostnadsfritt för frekvensbegränsning och attribueringsmätning
   * Prissatt till $0,35 CPM för utökade visningar (visningar som levereras enbart med enhetsdiagrammet [!DNL LiveRamp] i stället för på enheter som hittas inom målgruppssegmenten)

      Kursen visas på ditt kontokort.

## Personbaserad frekvenshantering

Med personbaserad frekvenshantering kan du ange frekvensgränser på personnivå, i stället för på enhetsnivå, för kontroll av medieexponering.

### Aktivera personbaserad frekvenshantering

* **kampanjer:** När du skapar en ny kampanj kan du ange en  [!UICONTROL Cross-Device Level] inställning. Aktivera [!UICONTROL Same Device] -> [!UICONTROL People] och välj ett enhetsdiagram. Det angivna enhetsdiagrammet används både för målinriktning mellan olika enheter på placeringsnivå och för personbaserad frekvenshantering på kampanj-, paket- och placeringsnivå. Frekvensintervallen gäller för alla en persons kända enheter.

Mer information finns i [Kampanjinställningar](/help/dsp/campaign-management/campaigns/campaign-settings.md).

När du har sparat en kampanj kan du inte ändra dess [!UICONTROL Cross Device Level]-inställning.

* **Paket:**  Du kan ange ytterligare frekvensgränser på paketnivå om du vill. DSP respekterar det striktaste frekvenstaket i kampanjhierarkin.

* **Placeringar:** Du kan också ange ytterligare frekvensomslag på placeringsnivån. DSP respekterar det striktaste frekvenstaket i kampanjhierarkin.

## Målgruppsbaserad anpassning

Med personbaserad målinriktning kan ni hitta kunder på både dator och mobil.

### Aktivera personbaserad målgruppsanpassning

* **kampanjer:** När du skapar en ny kampanj kan du ange en  [!UICONTROL Cross-Device Level] inställning. Aktivera [!UICONTROL Same Device] -> [!UICONTROL People] och välj ett enhetsdiagram. Det angivna enhetsdiagrammet används både för målinriktning mellan olika enheter på placeringsnivå och för personbaserad frekvenshantering.

Mer information finns i [Kampanjinställningar](/help/dsp/campaign-management/campaigns/campaign-settings.md).

* **Placeringar:** När du väljer målgruppsmål för en placering i en kampanj med ett angivet enhetsdiagram kan du med ett  [!UICONTROL Cross-Device Targeting] alternativ utöka målgruppsanpassningen för alla en persons kända enheter (enligt det enhetsdiagram som anges i kampanjinställningarna), även enheter som inte finns i de angivna segmenten.

### Konfigurera rapportering för personbaserad målgruppsanpassning

Du kan inkludera följande mått i anpassade rapporter:

* **Utökade exponeringar:** (I  [!UICONTROL Build Your Report] avsnittet under  [!UICONTROL Metrics] >  [!UICONTROL Std. Metrics]) Volymen av inkrementella visningar som levereras genom användning av ett enhetsdiagram (och som inte hittas inom de ursprungliga målgruppssegmenten). Det här måttet används också för att beräkna tillämpliga avgifter som är kopplade till användning av ett enhetsdiagram från tredje part.

   Om du vill ta reda på kostnaden för dina utökade avbildningar under en tidsperiod kan du köra en anpassad rapport som innehåller kolumnen [!UICONTROL Extended Impressions] och sedan multiplicera det totala antalet utökade avbildningar med 0,00035 USD ($0,35/1000 visningar).

   Den aggregerade kostnaden ingår också i kolumnen [!UICONTROL Billable Other Net Spend] (under [!UICONTROL Metrics] > [!UICONTROL Spend]), även om det måttet även inkluderar andra kampanjavgifter som du kan ha lagt till.

* **Enhetsdiagram:** (i  [!UICONTROL Build Your Report] avsnittet under  [!UICONTROL Dimensions] >  [!UICONTROL Campaign]) Det valda enhetsdiagrammet för en viss kampanj, ett visst paket eller en viss placering.

## Personbaserad attribueringsmätning

*Annonsörer med endast Advertising Cloud Conversion Tracking*

Med personbaserad attribuering kan du attribuera konverteringar som ägde rum på en annan enhet än den enhet som medieexponeringen inträffade på. Personbaserad attribueringsmätning är tillgänglig i alla DSP, Advertising Cloud Search och Advertising Cloud Creative för annonsörer som har implementerat Advertising Cloud-konverteringspixlar på sina webbplatser.

### Aktivera personbaserad attribueringsmätning

Om du vill aktivera attribueringsmätning mellan enheter kontaktar du kontohanteraren för Adobe. För [!DNL Adobe Device Co-op]-konton måste du ange ditt signerade [!DNL Adobe Device Co-op]-kontrakt och Experience Cloud [!DNL Organization ID] (kallades tidigare [!DNL IMS org ID]).

Så här ser du om ett annonserarkonto har konfigurerats att använda ett enhetsdiagram för attribueringsmätning:

1. Klicka på **[!UICONTROL Settings]>[!UICONTROL Advertiser]** på huvudmenyn.
1. Håll markören över annonsörraden och klicka på **[!UICONTROL Edit]**.
1. I avsnittet [!UICONTROL Integrations] i inställningarna för annonseraren kontrollerar du om inställningen [!UICONTROL Cross-Device Attribution] är aktiv.

   För aktiva integreringar anges enhetsdiagrammet.

### Ställ in konverteringsrapporter för attribut för konvertering mellan enheter

#### Inställningar för konverteringsrapport

När ett enhetsdiagram är aktiverat för attribueringsmätning innehåller [!UICONTROL Conversion]-rapporten en [!UICONTROL Cross-Device Breakout]-inställning som gör att du kan ta med upp till tre separata kolumner för varje konverteringsmått, inklusive:

* &lt;>Konvertering *>[!UICONTROL (tp)]: Innehåller det totala antalet konverteringar (totalt antal personer), som omfattar både konverteringar mellan enheter och konverteringar mellan enheter (om tillämpligt).* I rapporten läggs &quot;[!UICONTROL (tp)]&quot; till i konverteringsmeternamnet, regeltypen och konverteringstyperna i konverteringssökvägen (till exempel &quot;Responses(le)(tl)(tp)&quot;).

* &lt;>Konvertering *>[!UICONTROL (sd)]: (Valfritt) Inkluderar endast konverteringar för vilka endast en enhet spårades i konverteringssökvägen.* I rapporten läggs &quot;[!UICONTROL (sd)]&quot; till i konverteringsmeternamnet, regeltypen och konverteringstyperna i konverteringssökvägen (till exempel &quot;Responses(le)(tl)(sd)&quot;).

* &lt;>Konvertering *>[!UICONTROL (xd)]: (Valfritt) Inkluderar endast konverteringar för vilka mer än en enhet spårades i konverteringssökvägen.* I rapporten läggs &quot;[!UICONTROL (xd)]&quot; till i konverteringsmeternamnet, regeltypen och konverteringstyperna i konverteringssökvägen (till exempel &quot;Responses(le)(tl)(xd)).

#### Tolka konverteringsrapporten

Om du sorterar procentandelen av det totala antalet konverteringar mellan olika enheter ([!UICONTROL (xd)]/[!UICONTROL (tl)]) från hög till låg, kommer du att förstå vad som genererar konverteringar över genomsnittet för olika enheter. Du kan använda detta för att informera om din kreativa strategi eller målinriktningsstrategi så att meddelanden och kanalinvesteringar matchar användarens beteende.

* Paket - Se vilka paket som genererar mest totala konverteringar och vilka som har en hög andel konverteringar mellan olika enheter. Detta kan hjälpa er att förstå var ni ska satsa.

* Placeringar - Jämför placeringsprestanda och attribuering (en mobil webbannons kan till exempel leda till konverteringar på datorn). Utan ett enhetsdiagram för attribuering kan du missa en mobil webbpositions effekt på skrivbordskonverteringar, eller så kan den bli nedgrävd om de flesta av dina användare konverterar på datorn och inte på mobilwebben.

* Annonser - Upptäck vilka annonser som genererar högre konverteringar och kvantifiera deras värde och effekt i både webbläsare och mobilappsmiljöer.

* Webbplatser - Optimera för olika webbplatser i stället för att helt utesluta webbplatser manuellt. Om en webbplats driver konverteringar mellan olika enheter kan du se på vilka enheter detta beteende gäller.

* Erbjudanden - Förbättra den manuella optimeringen genom att kontrollera vilka lagererbjudanden som ger konverteringar mellan olika enheter och sedan avgöra om ni bör utöka er målinriktning för att inkludera fler enheter och kanaler i dessa avtal.

>[!MORELIKETHIS]
>
>* [Rapportinställningar](/help/dsp/reports/report-settings.md)
>* [Kampanjinställningar](/help/dsp/campaign-management/campaigns/campaign-settings.md)
>* [Paketinställningar](/help/dsp/campaign-management/packages/package-settings.md)
>* [Placeringsinställningar](/help/dsp/campaign-management/placements/placement-settings.md)
