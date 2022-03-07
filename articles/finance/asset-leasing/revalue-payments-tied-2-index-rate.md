---
title: Zmiana wartości opłat z tytułu wynajmu powiązanych ze stawką indeksowaną
description: W tym temacie opisano korektę dokonywaną w zobowiązaniu z tytułu wynajmu składnika majątku z prawem do użytkowania (PDU), gdy zmienne opłaty z tytułu wynajmu zmieniają się z powodu zmiany stawki indeksowanej.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 83684afbd5e11b890a59bc1469ddefffd1777c4e
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446990"
---
# <a name="revalue-lease-payments-that-are-linked-to-an-index-rate"></a>Zmiana wartości opłat z tytułu wynajmu powiązanych ze stawką indeksowaną

[!include [banner](../includes/banner.md)]

W tym temacie opisano korektę dokonywaną w zobowiązaniu z tytułu wynajmu składnika majątku z prawem do użytkowania (PDU), gdy zmienne opłaty z tytułu wynajmu zmieniają się z powodu zmiany stawki indeksowanej. Zobowiązanie z tytułu wynajmu i składniki majątku z prawem do użytkowania zostaną skorygowane w celu uwzględnienia nowych kwot płatności. Zgodnie z zasadami Accounting Standards Codification Topic 842 (ASC 842), które są standardem przyjętym w ogólnie przyjętych zasadach rachunkowości w Stanach Zjednoczonych (US GAAP), tylko opłaty zmienne rosną lub spadają wskutek zmiany stawki indeksowanej, chyba że istnieją dodatkowe zmiany w przepływach pieniężnych. Te dodatkowe zmiany mogą wynikać na przykład ze zmiany warunków wynajmu spowodowanych zmianą stóp procentowych. Aby uzyskać więcej informacji, zapoznaj się ze standardem ASC 842-10-55-225 oraz punktem 42(b) Międzynarodowego Standardu Sprawozdawczości Finansowej nr 16 (MSSF 16).

## <a name="adjust-lease-payments"></a>Korygowanie opłat z tytułu wynajmu

Wykonaj poniższe czynności, aby zmienić wartości opłat z tytułu wynajmu powiązanych ze stawką indeksowaną.

1. Aby uruchomić proces przeszacowania indeksu dla umowy wynajmu, wybierz kolejno opcje **Wynajem składnika majątku \> Okresowe \> Przeszacowanie stawki indeksowanej**.

    Zostanie wyświetlona strona **Przeszacowanie stawki indeksowanej**, na której widać wyświetlone poprzednie procesy przeszacowania indeksu dla umowy wynajmu. Informacje na tej stronie zawierają identyfikator procesu wygenerowany na podstawie konfiguracji numeracji, osobę prawną, liczbę skorygowanych ksiąg wynajmu, łączną korektę zobowiązań dla umów wynajmu zgodnych ze standardem MSSF 16 oraz łączne opłaty zmienne skorygowane dla umów najmu zgodnych z normą ASC 842.

2. Aby uruchomić przeszacowanie, w okienku akcji wybierz opcję **Przeszacowania indeksu dla wynajmu**.

    Zostanie wyświetlone okno dialogowe **Parametry przeszacowania indeksu**. W tym miejscu można filtrować i wybierać umowy wynajmu, grupy wynajmu i inne kryteria, które mają być używane podczas wybierania umów wynajmu do przeszacowania. Ponadto na karcie **Uruchom w tle** można skonfigurować proces przeszacowania indeksu w taki sposób, aby był uruchamiany wsadowo.

4. Wybierz filtry wybierania umów najmu, które mają zostać uwzględnione w przetwarzaniu w tle, a następnie kliknij przycisk **OK**.

    Zostanie wyświetlone okno dialogowe **Podgląd przeszacowania stawki indeksowanej** zawierające umowy wynajmu, które zostaną przeszacowane. Pokazuje także korekty aktywów i pasywów oraz korekty opłat zmiennych.
    
5. Aby zapobiec przeszacowywaniu umów wynajmu, zaznacz umowy, które **powinny** zostać przeszacowane. Jeśli nie zaznaczysz żadnych umów wynajmu, zostaną przeszacowane wszystkie umowy. Po zakończeniu kliknij przycisk **OK**, aby przeszacować umowy wynajmu.
6. Aby wyświetlić transakcje utworzone dla konkretnego procesu przeszacowania indeksu, wybierz identyfikator procesu, a następnie wybierz opcję **Transakcje**.

    Zostanie wyświetlone okno dialogowe zawierające szczegóły transakcji, które zostały utworzone podczas przetwarzania.

> [!NOTE]
> Można przeszacowywać tylko umowy wynajmu mające datę przeszacowania nie późniejszą niż data systemowa. System automatycznie ignoruje wszystkie umowy wynajmu, których data przeszacowania jest późniejsza niż data systemowa.

## <a name="asc-842-leases--index-revaluation"></a>Umowy wynajmu zgodne ze standardem ASC 842 — przeszacowanie indeksu

Aby wyświetlić efekty procesu przeszacowania umów wynajmu realizowanych zgodnie ze standardem ASC 842, otwórz harmonogram płatności dla umowy wynajmu. Na stronie są wyświetlane tylko opłaty zmienne, które zostały wprowadzone nie wcześniej niż w dniu zmiany daty przeszacowania z powodu przeszacowania indeksu. Harmonogramy amortyzacji pozostają niezmienione. Podczas tworzenia faktury zawierającej opłatę zmienną opłata ta jest księgowana po stronie debetowej na koncie księgowania opłat zmiennych. Ponadto kwota zmiennej opłaty jest dodawana do zapisu kredytowego księgowanego bezpośrednio względem dostawcy lub księgowana na koncie not zobowiązań, w zależności od konfiguracji księgi wynajmu.

Wiersze harmonogramu płatności na stronie szczegółów wynajmu są automatycznie aktualizowane o nowy wiersz wskazujący nową stawkę indeksowaną. Ponadto kolumna pokazuje, czy wiersz został utworzony ręcznie, czy za pomocą procesu przeszacowania indeksu.

## <a name="ifrs-16-leases--index-revaluation"></a>Umowy wynajmu zgodne ze standardem MSSF 16 — przeszacowanie indeksu

Aby wyświetlić efekty procesu przeszacowania umów wynajmu realizowanych zgodnie ze standardem MSSF 16, otwórz szczegóły skorygowanego wynajmu. Pola **Okres wynajmu** i **Okres użyteczności składnika majątku** zostały zaktualizowane, aby odzwierciedlały upływ czasu od daty rozpoczęcia lub daty modyfikacji do daty przeszacowania. Ponadto wiersze harmonogramu płatności zostały zaktualizowane w celu uwzględnienia nowych opłat z tytułu wynajmu, nowej stawki indeksowanej oraz sposobu utworzenia wiersza.

Można wyświetlić nowo wygenerowany harmonogram płatności rozpoczynający się w dniu przeszacowania oraz wyświetlić łączną zaktualizowaną kwotę płatności. Zostały również utworzone nowy harmonogram amortyzacji zobowiązań z tytułu wynajmu i harmonogram amortyzacji składnika majątku, aby odzwierciedlić skorygowany harmonogram płatności.

Wpis w arkuszu spowodował automatyczne zaksięgowanie wpisu w arkusza korekty na koncie zmiany opłat z tytułu wynajmu powiązanych z przeszacowaniem indeksu.
