---
title: Zasady pracy magazynowej
description: "Zasady kontroli pracy magazynowej określają, czy praca magazynowa jest tworzona przez procesy magazynowe na produkcji w oparciu o typ zlecenia pracy, lokalizację zapasów i produkt."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 7612003bc20f91f173629893750478b034cff27b
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---

# <a name="warehouse-work-policies"></a>Zasady pracy magazynowej

[!include[banner](../includes/banner.md)]


Zasady kontroli pracy magazynowej w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition określają, czy praca magazynowa jest tworzona przez procesy magazynowe na produkcji w oparciu o typ zlecenia pracy, lokalizację zapasów i produkt.

Ta zasada pracy kontroluje, czy praca magazynowa jest tworzona dla procesów magazynu w produkcji. Zasadę pracy można skonfigurować przy użyciu kombinacji **typów zleceń**, **lokalizacji zapasów** i **produktu**. Na przykład produkt L0101 jest zgłoszony jako ukończony do lokalizacji wyjściowej 001. Gotowy produkt jest później zużywany na podstawie innego zlecenia produkcyjnego w lokalizacji wyjściowej 001. W takim przypadku można skonfigurować zasadę pracy, która uniemożliwi tworzenie pracy odkładania wyrobów gotowych, gdy produkt L0101 zostanie zgłoszony jako gotowy do lokalizacji wyjściowej 001. Zasada pracy jest osobną jednostką, którą można opisać za pomocą następujących informacji:

-   **Nazwa zasady pracy**(unikatowy identyfikator zasady pracy)
-   **Typy zleceń** i **Metoda tworzenia pracy**
-   **Magazyny**
-   **Produkty**

## <a name="work-order-types"></a>Typy zleceń
Możesz wybrać spośród następujących typów zleceń:

-   Ukończono odkładanie wyrobów
-   Odłożenie produktu ubocznego i produktu towarzyszącego
-   Pobranie surowca

Pole **Metoda tworzenia pracy** ma wartość **Nigdy**. Ta wartość wskazuje, że zasada pracy uniemożliwi tworzenie pracy magazynowej dla wybranego typu zlecenia.

## <a name="inventory-locations"></a>Magazyny
Można wybrać lokalizację, do której ma zastosowanie zasada pracy. Jeśli z zasadą pracy nie zostanie skojarzona żadna lokalizacja, zasada nie ma zastosowania do żadnych procesów. Na stronie **Lokalizacje** można również zaznaczyć lub usunąć zaznaczenie zasady pracy dla określonej lokalizacji.

## <a name="products"></a>Produkty
Można wybrać produkt, do którego ma zastosowanie zasada pracy. Zasada pracy może dotyczyć wszystkich produktów lub wybranych produktów.

## <a name="example"></a>Przykład
W poniższym przykładzie istnieją dwa zlecenia produkcyjne, PRD-001 i PRD 00*2*. Zlecenie produkcyjne PRD-001 zawiera operację o nazwie **Montaż**, z której produkt SC1 jest zgłaszany jako gotowy do lokalizacji O1. Zlecenie produkcyjne PRD-002 ma operację o nazwie **Malowanie** i zużywa produkt SC1 z lokalizacji O1. Zlecenie produkcyjne PRD-002 zużywa także surowiec RM1 z lokalizacji O1. Surowiec RM1 jest przechowywany w lokalizacji magazynowej BULK-001 i zostanie pobrany do lokalizacji O1 za pomocą pracy magazynowej pobrania materiału. Praca pobierania jest generowana po zwolnieniu produkcji PRD-002. 

[![Zasady pracy magazynowej](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png) 

Planując skonfigurowanie zasady pracy magazynowej dla tego scenariusza, należy uwzględnić następujące informacje:

-   Praca magazynowa odłożenia wyrobów gotowych nie jest wymagana, jeżeli zgłaszasz produkt SC1 jako gotowy ze zlecenia produkcyjnego PRD-001 do lokalizacji O1. Wynika to z faktu, że operacja **Malowanie** dla zlecenia produkcyjnego PRD-002 zużywa produkt SC1 w tej samej lokalizacji.
-   Praca magazynowa pobrania surowca jest wymagana w celu przeniesienia surowca RM1 z lokalizacji magazynowej BULK-001 do lokalizacji O1.

Oto przykład zasady pracy, którą można skonfigurować z uwzględnieniem powyższych informacji.

|                                         |                                                       |
|-----------------------------------------|-------------------------------------------------------|
|**Nazwa zasady pracy**<br>                 |**Typy zleceń**<br>                               |
| Bez odłożenia 01     `                    |- Odłożenie gotowego wyrobu<br>                           |
|                                         |**Lokalizacje**<br>                                      |
|                                         |- O1   |                                               |
|                                         |**Produkty** <br>                                      |
|                                         |- SC1                                                  |

Poniższe procedury zawierają instrukcje krok po kroku dotyczące konfigurowania zasady pracy magazynowej dla tego scenariusza. Opisano również przykładową konfigurację prezentującą zgłaszanie zlecenia produkcyjnego jako gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.

## <a name="set-up-a-warehouse-work-policy"></a>Konfigurowanie zasady pracy magazynowej
Procesy magazynowe nie zawsze obejmują pracę magazynową. Poprzez zdefiniowanie pracy magazynowej można zablokować tworzenie pracy pobierania surowców i odkładania wyrobów gotowych dla zbioru produktów w określonych lokalizacjach. Do stworzenia tej procedury wykorzystano dane z firmy demonstracyjnej USMF. 

KROKI (21)

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| 1.  | Wybierz kolejno opcje Zarządzanie magazynem &gt; Ustawienia &gt; Praca &gt; Zasady pracy.        |
| 2.  | Kliknij przycisk Nowy.                                                                 |
| 3.  | W polu Nazwa zasady pracy wpisz „Bez pracy odłożenia”.                    |
| 4.  | Kliknij przycisk Zapisz.                                                                |
| 5.  | Kliknij przycisk Dodaj.                                                                 |
| 6.  | Na liście oznacz wybrany wiersz.                                        |
| 7.  | W polu Typ zlecenia wybierz wartość „Ukończono odkładanie wyrobów”.            |
| 8.  | Kliknij przycisk Dodaj.                                                                 |
| 9.  | Na liście oznacz wybrany wiersz.                                        |
| 10. | W polu Typ zlecenia wybierz opcję „Odłożenie produktu ubocznego i produktu towarzyszącego”. |
| 11. | Rozwiń sekcję Magazyny.                                    |
| 12. | Kliknij przycisk Dodaj.                                                                 |
| 13. | Na liście oznacz wybrany wiersz.                                        |
| 14. | Na liście magazynów wpisz „51”.                                         |
| 15. | W polu Lokalizacja wprowadź lub wybierz wartość „001”.                              |
| 16. | Rozwiń sekcję Produkty.                                               |
| 17. | W polu Wybór produktu wybierz opcję „Wybrane”.                         |
| 18. | Kliknij przycisk Dodaj.                                                                 |
| 19. | Na liście oznacz wybrany wiersz.                                        |
| 20. | W polu Numer pozycji wprowadź lub wybierz wartość „L0101”.                         |
| 21. | Kliknij przycisk Zapisz.                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Zgłaszanie zlecenia produkcyjnego jako gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny
Ta procedura zawiera przykład zgłaszania wyrobu gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny. Warunkiem wstępnym tego zadania jest istnienie odpowiedniej zasady pracy. Poprzednia procedura ilustruje konfigurowanie zasady pracy. 

KROKI (25)

<table>
<tbody>
<tr>
<td colspan="3"><strong>Podzadanie: Konfigurowanie lokalizacji wyjściowej.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Wybierz kolejno opcje Administrowanie organizacją &gt; Zasoby &gt; Grupy zasobów.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Na liście zaznacz grupę zasobów „5102”.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Kliknij przycisk Edytuj.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>W polu Magazyn wyjściowy wpisz „51”.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>W polu Lokalizacja wyjściowa wpisz „001”.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>Lokalizacja 001 nie jest lokalizacją kontrolowaną przez numer identyfikacyjny. Można skonfigurować lokalizację wyjściową niekontrolowaną za pomocą numeru identyfikacyjnego, ale tylko wtedy, gdy istnieje odpowiednia zasada pracy dla lokalizacji.</td>
</tr>
<tr>
<td colspan="3"><strong>Podzadanie: Tworzenie zlecenia produkcyjnego i zgłaszanie go jako gotowego.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Zamknij stronę.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Wybierz kolejno opcje Kontrola produkcji &gt; Zlecenia produkcyjne &gt; Wszystkie zlecenia produkcyjne.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Kliknij opcję Nowe zlecenie produkcyjne.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>W polu Numer pozycji wpisz „L0101”.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Kliknij Utwórz.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>W okienku akcji kliknij opcję Zlecenie produkcyjne.</td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td>Kliknij przycisk Szacuj.</td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td>Kliknij przycisk OK.</td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td>Kliknij przycisk Uruchom.</td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td>Kliknij kartę Ogólne.</td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td>W polu Automatyczne zużycie BOM zaznacz opcję „Nigdy”.</td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td>Kliknij przycisk OK.</td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td>Kliknij opcję Zgłoś jako gotowe.</td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td>Kliknij kartę Ogólne.</td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td>W polu Akceptacja błędu wybierz opcję Tak.</td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td>Kliknij przycisk OK.</td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td>W okienku akcji kliknij pozycję Magazyn.</td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td>Kliknij opcję Szczegóły pracy.</td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td>Po zgłoszeniu zlecenia produkcyjnego jako gotowego nie została wygenerowana żadna praca odłożenia. Dzieje się tak, ponieważ zdefiniowano zasadę pracy, która blokuje generowanie pracy, gdy produkt L0101 jest zgłaszany jako gotowy do lokalizacji 001.</td>
</tr>
</tbody>
</table>



