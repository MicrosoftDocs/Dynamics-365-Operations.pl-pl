---
title: Zapotrzebowania na zakup
description: W tym temacie opisano sposób, w jaki zapotrzebowania na zakup są obsługiwane w optymalizacji planowania.
author: t-benebo
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 0328342fbe322225a5ecb095d3b0165caa6d18d3
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469653"
---
# <a name="purchase-requisitions"></a>Zapotrzebowania na zakup

[!include [banner](../../includes/banner.md)]

Planowanie główne może uzupełniać zapasy dla zatwierdzonych zapotrzebowań na zakup. Dlatego aby pokryć zapotrzebowania na zakup, użytkownicy nie muszą używać przepływu pracy do tworzenia zamówień zakupu. Zapotrzebowania na zakup mogą być natomiast pokrywane przez planowanie główne. Dzięki tej funkcji zapotrzebowania na zakup mogą tworzyć zamówienia zakupu, zamówienia przeniesienia lub zlecenia produkcyjne, w zależności od wartości **typu planowanego zamówienia** ustawionej dla powiązanego produktu.

## <a name="enable-master-plans-to-include-requisitions"></a>Włączanie planów głównych z uwzględnieniem zapotrzebowań

Aby uwzględnić zapotrzebowania podczas obliczania zapotrzebowania dla planu głównego, wykonaj następujące kroki.

1. Przejdź do obszaru **Planowanie główne** \> **Ustawienia** \> **Plany** \> **Plany główne**.
1. Utwórz lub wybierz plan główny.
1. Na skróconej karcie **Ogólne** ustaw opcję **Uwzględnij zapotrzebowania** na *Tak*.
1. Powtórz kroki 2 i 3 dla każdego dodatkowego planu głównego, w którym chcesz uwzględnić zapotrzebowania.

## <a name="approved-requisitions-time-fence"></a>Zatwierdzony horyzont czasowy zapotrzebowań

*Zatwierdzony horyzont czasowy zapotrzebowań* określa, jak daleko wstecz (w dniach) plan główny będzie uwzględniał popyt z zatwierdzonych zapotrzebowań uzupełniania zapasów. Można ustawić zatwierdzony horyzont czasowy zapotrzebowania zarówno na poziomie grupy zapotrzebowania, jak i na poziomie planu głównego.

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a>Ustawianie horyzontu czasowego zatwierdzonych zapotrzebowań dla grupy zapotrzebowań

1. Przejdź do menu **Planowanie główne** \> **Konfiguracja** \> **Zapotrzebowanie** \> **Grupy zapotrzebowania**.
1. Utwórz lub wybierz grupę zapotrzebowania.
1. Na skróconej karcie **Inne** ustaw w polu **Horyzont czasowy zatwierdzonych zapotrzebowań (dni)** liczbę dni, która ma zostać w nim uwzględniona.
1. Powtórz kroki 2 i 3 dla każdej dodatkowej grupy zapotrzebowania, w której chcesz ustawić horyzont czasowy zatwierdzonych zapotrzebowań.

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a>Ustawianie horyzontu czasowego zatwierdzonych zapotrzebowań dla indywidualnych planów głównych

Po ustawieniu horyzontu czasowego zatwierdzonych zapotrzebowań dla pojedynczego planu głównego to ustawienie zastępuje ustawienie horyzontu czasowego dla dowolnej właściwej grupy zapotrzebowania.

1. Przejdź do obszaru **Planowanie główne** \> **Ustawienia** \> **Plany** \> **Plany główne**.
1. Utwórz lub wybierz plan główny.
1. Na skróconej karcie **Horyzonty czasowe w dniach** ustaw w polu **Horyzont czasowy zatwierdzonych zapotrzebowań (dni)** liczbę dni, która ma zostać w nim uwzględniona.
1. Powtórz kroki 2 i 3 dla każdego dodatkowego planu głównego, w której chcesz ustawić horyzont czasowy zatwierdzonych zapotrzebowań.

> [!IMPORTANT]
> **Dostępne wkrótce:** horyzonty czasowe zatwierdzonych zapotrzebowań nie są jeszcze obsługiwane podczas optymalizacji planowania. Dopóki nie będą one obsługiwane, wszystkie wartości podane w polu **Horyzonty czasowe zatwierdzonych zapotrzebowań (dni)** będą ignorowane.

## <a name="independent-supply-regardless-of-coverage-code"></a>Niezależne zaopatrzenie, niezależnie od kodu zapotrzebowania

Zapotrzebowania na zakup są zawsze pokrywane przez niezależne zamówienia planowane, niezależnie od kodu zapotrzebowania. Takie działanie zapewnia czytelną możliwość śledzenia i przepływów pracy między zapotrzebowaniami na zakupu i zamówieniami uzupełniania zapasów.

### <a name="example-1"></a>Przykład 1

Produkt jest tak ustawiony, że ma wartość **kodu zapotrzebowania** *Minimum/maksimum*. Ma one następujące stany zapasów i zapotrzebowania:

- Ilość dostępnych zapasów = 10.
- Minimalna ilość zapasów = 15.
- Maksymalna ilość zapasów = 20.
- Istnieje zapotrzebowanie na zakup jednej sztuki. Żądana data to data dzisiejsza.

Podczas planowania głównego tworzone są dwa planowane zamówienia: jedno na 10 sztuk w celu uzupełnienia zapasów do maksymalnej ilości, a drugie na jedną sztukę w celu uzupełnienia zapotrzebowania na zakup.

### <a name="example-2"></a>Przykład 2

Produkt jest tak ustawiony, że ma wartość **kodu zapotrzebowania** *Minimum/maksimum*. Ma one następujące stany zapasów i zapotrzebowania:

- Ilość dostępnych zapasów = 17.
- Minimalna ilość zapasów = 15.
- Maksymalna ilość zapasów = 20.
- Istnieje zapotrzebowanie na zakup jednej sztuki. Żądana data to data dzisiejsza.

Podczas planowania głównego tworzone jest jedno planowane zamówienie na jedną sztukę w celu uzupełnienia zapotrzebowania na zakup.

### <a name="example-3"></a>Przykład 3

Produkt jest tak ustawiony, że ma wartość **kodu zapotrzebowania** *Okres*, a długość okresu wynosi siedem dni. Ma on następujące stany zapasów, zamówienia sprzedaży i zapotrzebowania:

- Ilość dostępnych zapasów = 0.
- Istnieje zamówienie sprzedaży na pięć sztuk. Oczekiwana data wysyłki to dzisiaj plus jeden dzień.
- Istnieje zapotrzebowanie na zakup trzech sztuk. Żądana data to data dzisiejsza plus trzy dni.

Podczas planowania głównego tworzone są dwa planowane zamówienia: jedno na trzy sztuk w celu uzupełnienia zapotrzebowania na zakup, a drugie na pięć sztuk w celu uzupełnienia popytu w zamówieniu sprzedaży.

> [!NOTE]
> Po zaakceptowaniu zamówienia planowanego z oznaczoną transakcją zapotrzebowania na zakup aparat planowania przechowuje oznaczanie transakcji dla zapotrzebowania na zakup. Jeśli później dowiemy się, że w zaakceptowanym zamówieniu brakuje określonej ilości wymaganej do zrealizowania zapotrzebowania na zakup, system utworzy nowe planowane zamówienie dla tej różnicy.

Aby uzyskać dalsze informacje o zapotrzebowaniach na zakupu, zobacz [Omówienie zapotrzebowań na zakup](../../procurement/purchase-requisitions-overview.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]