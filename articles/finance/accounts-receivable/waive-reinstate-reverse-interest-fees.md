---
title: Uchylanie, przywracanie lub wycofywanie odsetek lub opłat
description: W tym artykule wyjaśniono, jak uchylać, przywracać i wycofywać opłaty w postaci odsetek i opłat.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInterestJourList
audience: Application User
ms.reviewer: roschlom
ms.custom: 59461
ms.assetid: 25ec29f3-e3ea-4abb-bf6b-f6240873b315
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 080b46e69d9959f7a10a291552603f80071a934a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003238"
---
# <a name="waive-reinstate-or-reverse-interest-fees"></a>Uchylanie, przywracanie lub wycofywanie odsetek lub opłat

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak uchylać, przywracać i wycofywać opłaty w postaci odsetek i opłat.

Za pomocą przycisków na karcie **Windykacja** na stronie listy **Wszyscy odbiorcy** można uchylać, wycofywać lub przywracać opłaty:

-   Uchylone opłaty są darowane. Można uchylić opłatę, jeśli np. odbiorca ją kwestionuje, a musi być zachowana dobra relacja biznesową z odbiorcą.
-   Przywrócone opłaty stają się należne ponownie. Można przywrócić opłaty, które zostały wcześniej uchylone. Może zajść potrzeba przywrócenia opłat, jeśli okaże się, że powinny one były zostać uchylone.
-   Wycofane opłaty są usuwane z konta odbiorcy i nie są już należne. Opłaty można wycofywać, jeśli na przykład wybrano złą stopę odsetek do obliczania kwoty, którą jest winien odbiorca. Za pomocą oddzielnego procesu można przeliczyć odsetki i utworzyć notę odsetkową z nowymi opłatami dla odbiorcy.

Wszystkie te działania powodują modyfikację noty odsetkowej. Nota odsetkowa to dokument biznesowy, który informuje odbiorcę o obciążeniu jego konta odsetkami lub opłatami. W przypadku uchylenia lub wycofania opłat lub odsetek automatycznie tworzona jest faktura korygująca do rozliczenia opłat. W przypadku przywracania uchylonych opłat automatycznie tworzona jest faktura z kwotą debetu w celu przywrócenia opłat, które jest winien odbiorca. Poniżej opisano wyniki każdej akcji.

| Akcja                                                                                                                                                                                                            | Wynik dla odbiorcy                                                                                             | Przetwórz                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Uchyl noty odsetkowe w całości, w tym wszystkie opłaty i odsetki, które noty zawierają –lub– Wybierz i uchyl transakcje odsetek i opłat będące częścią not odsetkowych.                                        | Opłaty są darowane.                                                                                           | Zostanie utworzona faktura korygująca lub korekta faktury dla odbiorcy. Faktura korygująca zostanie użyta do automatycznego rozliczenia wybranej noty odsetkowej lub transakcji odsetek lub opłat. Rozliczona kwota jest równa łącznej kwocie opłat minus ewentualne poprzedzające płatności dokonane przez odbiorcę, minus ewentualne kwoty, które poprzednio zostały uchylone lub odpisane. Jeśli kwota faktury korygującej przekracza to, co jest winien odbiorca, można konwertować fakturę korygującą na fakturę od dostawcy. Następnie można przekazać zwrot do odbiorcy.                                                       |
| Przywróć noty odsetkowe w całości, w tym wszystkie opłaty i odsetki, które noty zawierają. –lub– Wybierz i przywróć transakcje odsetek i opłat będące częścią not odsetkowych.                                | Uchylona kwota staje się ponownie należna.                                                                                     | Tworzona jest faktura z kwotą debetu, następnie kwota ta jest automatycznie rozliczana w odniesieniu do opłat, które poprzednio uchylono. Faktyczne noty odsetkowe nie są przywracane. Zamiast tego zostanie utworzona faktura, która pokazuje należną kwotę od odbiorcy Faktury korygujące lub korekty faktur, które zostały utworzone w celu rozliczenia uchylonych odsetek nadal mogą istnieć, jeśli nie zostały użyte do rozliczenia not odsetkowych. Gdy taka sytuacja ma miejsce, wartości oczekujących faktur korygujących są anulowane. Wartości oczekujących faktur korygujących zazwyczaj są automatycznie rozliczane, gdy noty odsetkowe są uchylane. Jednak niezapłacona faktura korygująca może istnieć, jeśli odbiorca zapłacił za notę odsetkową pomimo tego, że zakwestionowały opłaty. |
| Wycofaj całe noty odsetkowe. –lub– Wycofaj wybrane transakcje odsetek będące częścią not odsetkowych. **Uwaga:** Nie ma możliwości wycofywania opłaty. Można jednak wycofać całą notę odsetkową, zawierającą opłatę. | Opłaty nie są już należnością od odbiorcy. Jednak opłaty staną się ponownie należne po ponownym obliczeniu odsetek. | Proces jest taki sam, jak uchylenie not odsetkowych lub wybranych transakcji odsetek. Zostanie utworzona faktura korygująca lub korekta faktury dla odbiorcy. Ta faktura korygująca umożliwia automatyczne rozliczenie noty odsetkowej. Za pomocą oddzielnego procesu można ponownie obliczyć odsetki i utworzyć nową notę odsetkową.                                                                                                                                                                                                                                                                                                                                                                                              |

> [!NOTE] 
> Można również używać oddzielnego procesu do odpisania nieściągalnych długów. W procesie tym wszystkie transakcje odbiorcy są oznaczane do rozliczenia, tzn. nie następuje jedynie uchylenie opłat będących częścią not odsetkowych.

## <a name="adjust-interest-for-invoices"></a>Korygowanie odsetek dla faktur
Oprócz korygowania not odsetkowych można również usuwać odsetki na fakturach za pomocą jednego z następujących procesów. Oba te procesy także korygują powiązane noty odsetkowe.

### <a name="correct-an-invoice-that-has-associated-interest"></a>Korygowanie faktury z powiązanymi odsetkami

Możliwe jest korygowanie zaksięgowanej faktury, która jest uwzględniona w nocie odsetkowej. Ten proces kopiuje szczegóły z istniejącej faktury do nowej, dzięki czemu można wprowadzić tylko żądane korekty. Faktura zostanie anulowana i zostanie utworzona nowa faktura. Odsetki od transakcji także są wycofywane w nocie odsetkowej, jeśli nota odsetkowa została zaksięgowana. 

Można dokonać korekty za pomocą przycisku **Poprawianie faktury** w okienku akcji faktury niezależnej. Ten przycisk jest dostępny tylko jeśli wybrany jest klucz konfiguracji **Poprawianie faktury niezależnej**

### <a name="reverse-a-customer-transaction-that-has-associated-interest"></a>Wycofywanie transakcji odbiorcy wraz ze skojarzonymi odsetkami

Ten proces służy do wycofywania transakcji odbiorcy na fakturze, gdy faktura została utworzona niepoprawnie. Jeśli wycofana transakcja odbiorcy obejmuje odsetki zawarte na nocie odsetkowej, a nota odsetkowa została zaksięgowana, odsetki od transakcji także są wycofywane w nocie odsetkowej. Nota odsetkowa zostanie anulowana, jeśli nie została zaksięgowana. 

Można wycofać transakcje odbiorcy za pomocą przycisku **Wycofaj** na stronie **Transakcji odbiorcy**.

## <a name="waive-or-reinstate-interest-notes"></a>Uchylanie lub przywracanie not odsetkowych
Można uchylić lub przywrócić wszystkie opłaty na wybranych notach odsetkowych. W przypadku uchylenia opłat łączna kwota do uchylenia nie może przekraczać limitów kwot, które zostały ustawione. Można przywrócić notę odsetkową, tylko jeśli została wcześniej uchylona. 

Można uchylić lub przywrócić noty odsetkowe za pomocą przycisku **Nota odsetkowa** na karcie **Windykacja** na stronie **Odbiorca**.

## <a name="waive-or-reinstate-interest-transactions"></a>Uchylanie lub przywracanie transakcji odsetek
Można uchylić lub przywrócić określone transakcje odsetek na nocie odsetkowej zamiast korygować wszystkie opłaty na nocie odsetkowej. W przypadku uchylenia opłat łączna kwota do uchylenia nie może przekraczać limitów kwot, które zostały ustawione. Można przywrócić transakcję odsetek, tylko jeśli została wcześniej uchylona. 

Można uchylić lub przywrócić noty odsetkowe za pomocą przycisku **Odsetki transakcji** na karcie **Windykacja** na stronie **Odbiorca**.

## <a name="waive-or-reinstate-fees"></a>Uchylenie lub przywrócenie opłat
Można uchylić lub przywrócić określone opłaty na nocie odsetkowej zamiast korygować wszystkie opłaty na nocie odsetkowej. W przypadku uchylenia opłat łączna kwota do uchylenia nie może przekraczać limitów kwot, które zostały ustawione. Istnieje możliwość przywrócenia opłaty, tylko jeśli została poprzednio uchylona. 

Można uchylić lub przywrócić noty odsetkowe za pomocą przycisku **Opłata** na karcie **Windykacja** na stronie **Odbiorca**.

## <a name="reverse-interest-notes"></a>Wyksięguj noty odsetkowe
Można wycofać wszystkie opłaty na wybranych notach odsetkowych. Wycofane opłaty są usuwane z konta odbiorcy i nie są już należne. Po wycofaniu noty odsetkowej, można ponownie obliczyć odsetki i utworzyć nową notę odsetkową. 

Można wycofać noty odsetkowe za pomocą przycisku **Nota odsetkowa** na karcie **Windykacja** na stronie **Odbiorca**.

## <a name="reverse-interest-transactions"></a>Wycofanie transakcji odsetek
Można wycofać wszystkie wybrane przez użytkownika transakcje odsetek. Wycofane opłaty są usuwane z konta odbiorcy i nie są już należne. Po wycofaniu transakcji, można ponownie obliczyć odsetki i utworzyć nową notę odsetkową.

Można wycofać odsetki transakcji za pomocą przycisku **Odsetki transakcji** na karcie **Windykacja** na stronie **Odbiorca**.

## <a name="view-the-history-of-adjustments-for-charges-that-were-waived-reinstated-or-reversed"></a>Wyświetlanie historii korekt dla opłat, które zostały uchylone, wycofane lub przywrócone.
Możesz przejrzeć szczegółową historię korekt not odsetkowych, na przykład informacje o użytkowniku, który wprowadził korektę, typie korekty, kwocie oraz czasie wprowadzenia korekty. Na przykład można wyświetlić poprzednie korekty, które zostały wprowadzone dla noty odsetkowej przed utworzeniem nowej noty odsetkowej. 

Można wycofać odsetki transakcji za pomocą przycisku **Historia** na karcie **Windykacja** na stronie **Odbiorca**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]