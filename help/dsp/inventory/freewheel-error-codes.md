---
title: Felkoder för [!DNL FreeWheel] Ad Submissions
description: Referera felkoderna som returneras för annonsinskick till [!DNL FreeWheel].
feature: DSP Private Inventory, DSP Deal IDs
exl-id: null
source-git-commit: d10e1c24ee7c93eaab3fd4fefe853860226cc8e2
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 2%

---

# Felkoder för [!DNL FreeWheel]-annonseringar

Felmeddelandena för misslyckade annonsinskick kan komma från antingen Advertising Cloud DSP eller [!DNL FreeWheel]. Felmeddelanden visas i kolumnen [!UICONTROL API Response] i dialogrutan [[!UICONTROL Freewheel Status]](freewheel-check-status.md).

## Advertising Cloud DSP Internal Errors

| Felmeddelande | Beskrivning | Nästa steg |
|--- |--- |--- |
| [!DNL Väntar på statussvar från [!DNL FreeWheel]] | [!DNL FreeWheel] har ännu inte svarat att överföringen lyckades eller misslyckades. | Kontrollera status igen om 10 minuter. |
| [!DNL The submitted ad does not have a clock number assigned.] | [!DNL FreeWheel] godkänner inte annonser i Storbritannien utan tilldelade klocknummer. | Tilldela annonsen ett klocknummer och skicka sedan annonsen igen. |
| [!DNL The ad you are attempting to submit has not yet finished transcoding. Please wait ten minutes then try again.] | Transcoder hade inte slutfört omkodningen av annonsen när du försökte skicka annonsen. | Vänta i tio minuter och skicka sedan annonsen igen. |
| [!DNL The deal id you input is not setup as a guaranteed feed. Please submit guaranteed deals only.] | Det inlämnade anbudet är inte utformat som ett programmatiskt garanterat avtal. [!DNL FreeWheel] accepterar endast garanterade erbjudanden. | Konfigurera erbjudande-ID som ett programmatiskt garanterat erbjudande. Annonsen skickas automatiskt till [!DNL FreeWheel] när du sparar den programmatiska garanterade standardplaceringen i slutet av arbetsflödet för erbjudande-ID. |
| [!DNL Invalid external_deal_id:] \&lt;deal_id> | Det skickade erbjudande-ID:t finns inte eller är inte aktivt i Adobe. | Se till att erbjudandet är aktivt och skicka sedan in annonsen igen. |
| [!DNL \[public_id=]\&lt;deal>] finns inte | Antals-ID:t som skickades finns inte på [!DNL FreeWheel]-sidan. | Kontakta din [!DNL FreeWheel]-representant för att bekräfta erbjudande-ID:t. |
| [!DNL Ad with identifier] \&lt;>annonsnamn *\>  [!DNL was not found.]* | Den inskickade annonsnyckeln finns inte eller är inte aktiv i Adobe. | Hitta rätt annonsnyckel och skicka sedan annonsen igen. |
| [!DNL Pending Submission] | Inlämningen väntar fortfarande. | Uppdatera sidan. |

{style=&quot;table-layout:auto&quot;}

## FreeWheel API-fel

| Code | Betydelse | Beskrivning | Nästa steg |
|--- |--- |--- |--- |
| 401 | Obehörig | Felaktiga, saknade eller ogiltiga autentiseringsuppgifter. | Kontakta din kontoansvarige på Adobe. |
| 403 | Förbjuden | Servern förstod begäran men vägrar godkänna den. | Kontakta din kontoansvarige på Adobe. |
| 404 | Hittades inte | Resursen du begärde är inte tillgänglig. Om Creative ID:t inte hittas i åtgärden PUT returneras 404. | Kontakta din kontoansvarige på Adobe. |
| 405 | Metoden tillåts inte | En begäran gjordes om en resurs med en begärandemetod som inte stöds av den resursen (till exempel med GET på en metod som kräver att data skickas av POSTEN eller med PUT på en skrivskyddad resurs). | Kontakta din kontoansvarige på Adobe. |
| 408 | Timeout för begäran | En timeout uppstod när den här begäran bearbetades. Timeout orsakas oftast av samtidiga begäranden om exklusiv åtkomst till vissa resurser. | Skicka begäran igen när du får den här statusen. Kontakta din kontoansvarige på Adobe om problemet kvarstår. |
| 422 | Enhet som inte kan bearbetas | Ogiltig resurs. Det här felet inträffar när begärandetexten är ogiltig eller när den skapade/uppdaterade resursen är ogiltig (t.ex. om det inte gick att hitta något avtal-ID). Mer information finns i [FreeWheel API 422-fel](#freewheel-422-errors). | Kontakta din kontoansvarige på Adobe. |
| 500 | Internt serverfel | API-systemfel. | Kontakta din kontoansvarige på Adobe. |

{style=&quot;table-layout:auto&quot;}

## FreeWheel API 422-fel {#freewheel-422-errors}

| Code | HTTP-kod | Beskrivning |
|--- |--- |--- |
| DATA_UNMARUST_FAILURE | 422 | Begärandedata är ogiltigt json-format. Mer information finns i felmeddelandet. |
| DATA_VALIDATION_FAILURE | 422 | Begärandedata saknar obligatoriska fält eller har en ogiltig datatyp. Mer information finns i felmeddelandet. |
| DATA_DEAL_INVALID | 422 | Avtalet är felaktigt konfigurerat eller finns inte. Mer information finns i felmeddelandet. |
| DATA_DEAL_GET_FAILURE | 422 | Avtalet hittades inte eller så har konfigurationen ett problem. Mer information finns i felmeddelandet. |
| DATA_CREATIVE_INGEST_FAILURE | 422 | Den kreativa URL:en är ogiltig. Mer information finns i felmeddelandet. |
| DATA_CREATIVE_LINK_FAILURE | 422 | De kreativa var inte länkade till annonsenhetens noder. Mer information finns i felmeddelandet. |
| DATA_CREATIVE_UPDATE_FAILURE | 422 | Kreativiteten uppdaterades inte. Mer information finns i felmeddelandet. |
| DATA_DSP_GET_FAILURE | 422 | DSP finns inte i systemet. |
| DATA_CREATIVE_UNLINK_FAILURE | 422 | Den kreativa delen länkades inte bort från annonsenheterna. |
| DATA_CREATIVE_DELETE_FAILURE | 422 | Kreativiteten togs inte bort. |
| DATA_CREATIVE_DETECTION_FAILURE | 422 | Det gick inte att hitta URL:en. |
| DATA_ENTITY_NOT_FOUND | 422 | Den kreativa finns inte. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>
>* [Översikt över hur man ställer in garantierbjudanden i FreeWheel](/help/dsp/inventory/freewheel-overview.md)
>* [Acceptera ett avtal i Inkorgen för avtal-ID](deal-id-inbox-accept.md)
>* [Skicka en annons för ett program med garanterad programmering till FreeWheel](/help/dsp/inventory/freewheel-submit.md)
>* [Kontrollera status för annonser  [!DNL FreeWheel] för programmatiska erbjudanden](/help/dsp/inventory/freewheel-check-status.md)
