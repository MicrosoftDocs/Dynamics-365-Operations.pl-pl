---
title: Reguły rozliczania
description: W tym artykule opisano cztery reguły rozliczania stosowane do zużycia surowców.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 89fd38ea6d2c1635e9d8974ab99c2e4cdae4d6be
ms.sourcegitcommit: 8d072505f66f507aafbaae65bedf3b530eb6cb7b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9266437"
---
# <a name="flushing-principles"></a>Reguły rozliczania

[!include [banner](../includes/banner.md)]

Reguły rozliczania odzwierciedlają różne strategie zużycia surowców wykorzystywanych w procesach produkcji. Zużycie to proces obejmujący odejmowanie materiałów z dostępnych zapasów i ustawianie w zużywanych materiałach wartości **Praca w toku** (PWT) dla zleceń produkcyjnych i szarż produkcyjnych. Surowce są zazwyczaj zużywane z lokalizacji skonfigurowanej dla procesu wykorzystującego materiał. Ta lokalizacja jest nazywana lokalizacją wejściową produkcji.

Przed zużyciem materiały są przenoszone do lokalizacji wejściowej. Poniższa ilustracja pokazuje ten proces.

[![scenario4a.](./media/scenario4a.png)](./media/scenario4a.png)

1. Magazyn materiałów
2. Pobranie surowca
3. Lokalizacja przyjęcia z produkcji
4. Zużycie surowca
5. Proces produkcji

Zużycie materiałów jest kontrolowane przez cztery następujące reguły rozliczania:

- Ręcznie
- Rozpocznij
- Zakończenie
- Dostępne w lokalizacji

Reguły rozliczania są konfigurowane w hierarchii wartości domyślnych. Hierarchia rozpoczyna się od zwolnionego produktu, gdzie reguła rozliczania ma wartość **Rozpoczęcie**. W wierszu listy składowej (BOM) lub formuły reguła rozliczania pobrana z produktu może zostać ręcznie zastąpiona. Domyślna reguła rozliczania w wierszach BOM produkcji lub wierszach formuły szarży produkcyjnej jest pobierana z produktu lub ręcznie wprowadzonych wartości w BOM lub formułach.

## <a name="description-of-the-flushing-principles"></a>Opis reguł rozliczania

### <a name="manual"></a>Ręcznie
Reguła rozliczania Ręcznie wskazuje, że rejestracja zużycia materiałów jest operacją ręczną. Ta reguła ma zastosowanie, jeśli na przykład chcesz śledzić czas, a na potrzeby śledzenia trzeba uwzględniać ilość zużytych materiałów z numerów partii lub numerów seryjnych. Ręczne zużycie jest rejestrowane w arkuszu listy pobrania produkcji. Dla towarów z włączoną funkcją procesów magazynowych (WMS) można stosować przepływ ręczny.

### <a name="start"></a>Uruchom
Reguła rozliczania Rozpoczęcie wskazuje, że materiał będzie automatycznie zużywany po rozpoczęciu zlecenia produkcyjnego. Zużywana ilość materiału jest proporcjonalna do ilości, z którą rozpoczęto proces. Jeśli reguła rozliczania Rozpoczęcie jest używana razem z systemem wykonywania produkcji, może również służyć do rozliczania materiałów podczas uruchamiania operacji lub zadania przetwarzania. Ta reguła ma zastosowanie, jeśli na przykład odchylenie zużycia jest nieznaczne, materiały mają niską wartość, nie jest wymagane śledzenie lub operacje są krótkotrwałe. 

### <a name="finish"></a>Zakończenie
Reguła rozliczania Zakończenie wskazuje, że materiał będzie automatycznie zużywany z chwilą zgłoszenia zlecenia produkcyjnego jako gotowego lub gdy operacja, w której ustawiono zużywanie materiału, zostanie zarejestrowana jako ukończona. Zużywana ilość materiału jest proporcjonalna do ilości zgłoszonej jako wyroby gotowe. Jeśli reguła rozliczania Zakończenie jest używana razem z systemem wykonywania produkcji, może również służyć do rozliczania materiałów z chwilą zakończenia operacji lub zadania przetwarzania. Ta reguła ma zastosowanie w tych samych sytuacjach, jak reguła Rozpoczęcie. Jednak reguła Zakończenie jest przeznaczona dla operacji o dłuższym czasie trwania, gdzie materiały nie powinny być wysyłane do PWT przed zakończeniem operacji.

> [!NOTE]
> Nie można stosować zasady płukania Finish razem z elementami planowania. Zamiast tego zalecamy stosowanie zasady Rozpocznij płukanie. Pozycje planowania mają typ produkcji *pozycja planowania* i tylko produkty towarzyszące i produkty uboczne mogą być zgłaszane jako gotowe w szarżach produkcyjnych utworzonych dla pozycji planowania.

### <a name="available-at-location"></a>Dostępne w lokalizacji
Reguła rozliczania Dostępne w lokalizacji wskazuje, że materiał będzie automatycznie zużywany z chwilą zarejestrowania jako pobranego do produkcji. Materiał jest rejestrowany jako pobrany z lokalizacji z chwilą ukończenia pracy pobrania surowca lub gdy materiał jest dostępny w lokalizacji wejściowej produkcji, a wiersz materiału został zwolniony do magazynu. Lista pobrania wygenerowana w trakcie procesu jest księgowana w zadaniu wsadowym. Ta reguła ma zastosowanie, jeśli na przykład masz wiele działań pobrania do jednego zlecenia produkcyjnego. W takim wypadku nie trzeba ręcznie aktualizować listy pobrania i można uzyskać bieżący obraz saldo PWT.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
