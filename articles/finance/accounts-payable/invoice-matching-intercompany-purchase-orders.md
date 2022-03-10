---
title: Uzgadnianie faktur i międzyfirmowe zamówienia zakupu
description: Firmę kupującą, która uczestniczy w transakcjach handlu międzyfirmowego, można skonfigurować tak, aby używała uzgadniania faktur w rozrachunkach z dostawcami. W takim przypadku muszą być spełnione równocześnie wymagania dotyczące księgowania dla handlu międzyfirmowego i uzgadniania faktur w rozrachunkach z dostawcami, aby było można zaksięgować faktury od dostawcy międzyfirmowego.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: twheeloc
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e884e96e1275f9162b642bbe48c2d891c6434002
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109975"
---
# <a name="invoice-matching-and-intercompany-purchase-orders"></a>Uzgadnianie faktur i międzyfirmowe zamówienia zakupu

[!include [banner](../includes/banner.md)]

Firmę kupującą, która uczestniczy w transakcjach handlu międzyfirmowego, można skonfigurować tak, aby używała uzgadniania faktur w rozrachunkach z dostawcami. Gdy pole **Księguj fakturę z rozbieżnościami** na stronie **Parametry modułu rozrachunków z dostawcami** jest ustawione na **Wymagaj zatwierdzania**, zostanie przeprowadzona weryfikacja uzgadniania faktur. W takim przypadku muszą być spełnione równocześnie wymagania dotyczące księgowania dla handlu międzyfirmowego i uzgadniania faktur w rozrachunkach z dostawcami, aby było można zaksięgować faktury od dostawcy międzyfirmowego.

Przykłady w tym temacie używają następującej konfiguracji handlu międzyfirmowego:
-   Fabrikam-Zakup jest firmą kupującą.
-   Fabrikam-Sprzedaż jest firmą sprzedającą.
-   Odbiorca 4020 jest zarejestrowany w firmie Fabrikam-Sprzedaż.
-   Dostawca 3024 jest zarejestrowany w firmie Fabrikam-Zakup.
-   W firmie Fabrikam-Zakup określono informacje międzyfirmowe dla dostawcy 3024. Firma Fabrikam-Sprzedaż jest określona jako odbiorca, a odbiorca 4020 jest określony jako konto odbiorcy odpowiadająca firmie Fabrikam-Zakup.
-   W firmie Fabrikam-Sprzedaż określono informacje międzyfirmowe dla odbiorcy 4020. Firma Fabrikam-Zakup jest określona jako odbiorca, a dostawca 3024 jest określony jako konto dostawcy odpowiadające firmie Fabrikam-Sprzedaż.

W poniższych przykładach zastosowano następujące ustawienia dotyczące uzgadniania faktur od dostawców dla firmy Fabrikam-Zakup:
-   Na stronie **Parametry modułu rozrachunków** z dostawcami wybrana jest opcja **Włącz weryfikację uzgadniania faktur**.
-   Na stronie **Parametry modułu rozrachunków z dostawcami** pole **Księguj fakturę z rozbieżnościami** ma wartość **Wymagaj zatwierdzania**.
-   Wartość procentowa ceny jednostkowej dla firmy wynosi 2 procent.

## <a name="example-price-matching-and-intercompany-trade"></a> Przykład: Uzgadnianie cen i handel międzyfirmowy
Kwoty netto dla faktury z międzyfirmowej faktury od dostawcy i międzyfirmowej faktury dla odbiorcy muszą być takie same. Wymaganie to ma charakter nadrzędny wobec wszelkich dozwolonych możliwości dokonywania akceptacji lub wartości procentowych rozbieżności cen w procesie uzgadniania faktur. Można na przykład wykonać następujące kroki.
1.  W firmie Fabrikam-Zakup utwórz zamówienie sprzedaży ZS888 dla odbiorcy 4020. Międzyfirmowe zamówienia zakupu MZZ222 jest tworzone automatycznie dla dostawcy 3024 w firmie Fabrikam-Zakup, a międzyfirmowe zamówienie sprzedaży MZS888 jest automatycznie tworzone w firmie Fabrikam-Sprzedaż.
2.  W Fabrikam-Sprzedaż zarejestruj, że towary zostały otrzymane i zaksięguj dokument dostawy. Stan dokumentu MZS888 zostaje zmieniony na Dostarczone. Stan dokumentu MZZ222 zostaje zmieniony na Otrzymane.
3.  W firmie Fabrikam Sales zaktualizuj fakturę dla ICSO888. Cena jednostkowa wynosi 0,45 i aktualizowanych jest 100 jednostek.
4.  W firmie Fabrikam-Zakup utwórz fakturę dla MZZ222. Przypadkowo zmieniasz cenę netto z 45,00 na 54,00. Pojawia się ikona wskazująca, że cena przekracza dozwoloną wartość procentową rozbieżności cen (dozwolona rozbieżność to 2%).
5.  Na stronie **Szczegóły uzgadniania faktur** zaznacz opcję zatwierdzania księgowania z rozbieżnościami w uzgadnianiu. Na stronie **Faktura dostawcy** kliknij przycisk **OK**. Jeśli faktura od dostawcy nie była międzyfirmową fakturą od dostawcy, księgowanie powiedzie się. Ponieważ jednak chodzi o międzyfirmową fakturę od dostawcy księgowanie kończy się niepowodzeniem. W handlu międzyfirmowym sumy faktur międzyfirmowych na międzyfirmowym zamówieniu sprzedaży muszą być równe z sumami na odpowiednim międzyfirmowym zamówieniu zakupu. Aby rozwiązać ten problem, popraw cenę netto na fakturze z powrotem na wartość domyślną 45,00.

## <a name="example-quantity-matching-with-intercompany-trade"></a> Przykład: Uzgadnianie ilości w handlu międzyfirmowym.
Ilości na międzyfirmowym zamówieniu zakupu i międzyfirmowym zamówieniu sprzedaży muszą być równe. Wymaganie to ma charakter nadrzędny wobec wszelkich dozwolonych możliwości dokonywania akceptacji. W poniższym przykładzie zastosowano następującą konfigurację dla handlu międzyfirmowego:
-   W firmie Fabrikam-Zakup zasada działania w przypadku zamówienia zakupu dla dostawcy 3024 została ustawiona na automatyczne księgowanie zarówno oryginalnej faktury dla odbiorcy, jak i międzyfirmowej faktury od dostawcy.

W poniższym przykładzie zastosowano następujące dodatkowe ustawienia dotyczące uzgadniania faktur od dostawców dla firmy Fabrikam-Zakup:
-   Na stronie **Grupy modeli pozycji** dla grupy modeli, która jest używana przez artykuł B-R14 wybrana jest opcja **Wymagania dotyczące przyjęcia**.
-   Dostępna ilość artykułu B-R14 wynosi 0 (zero).

Można na przykład wykonać następujące kroki.
1.  W firmie Fabrikam-Zakup utwórz zamówienie sprzedaży ZS999 dla odbiorcy 4020. Zamówienie zawiera jedną pozycję: 100 baterii (artykuł B-R14) po cenie jednostkowej 1,00. W firmie Fabrikam-Zakup zostaje automatycznie utworzone międzyfirmowe zamówienie zakupu MZZ333 dla dostawcy 3024, a w firmie Fabrikam-Sprzedaż zostaje automatycznie utworzone międzyfirmowe zamówienie sprzedaży MSZ999.
2.  W firmie Fabrikam-Sprzedaż dokonaj procedury aktualizacji faktury z MZS999. Księgowanie nie powiodło się, ponieważ artykuł jest niedostępny w magazynie i nie został jeszcze odebrany. Dlatego nie da się zaktualizować informacji finansowych.
3.  W firmie Fabrikam-Sprzedaż zarejestruj odebranie towarów i zaksięguj dokument dostawy dla MZS99. Dokument przyjęcia produktów dla MZZ333 jest automatycznie księgowany w firmie Fabrikam-Zakup. W firmie Fabrikam-Zakup odebrana ilość artykułu B-R14 zostaje zmieniona na 100.
4.  W firmie Fabrikam-Sprzedaż dokonaj procedury aktualizacji faktury z MZS999. Księgowanie powiedzie się w obu podmiotach prawnych. W firmie Fabrikam-Zakup kupowana ilość artykułu B-R14 zmienia się na 100. 







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
