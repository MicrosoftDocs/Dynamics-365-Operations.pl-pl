---
title: Uzgodnienia finansowe w sklepach detalicznych
description: W tym temacie opisano uzgodnienia finansowe w sklepach detalicznych dla punktu sprzedaży dla rozwiązania Microsoft Dynamics 365 Commerce.
author: anpurush
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0f57f3119039337922dcd4035e1c4d64e6ae7295
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792398"
---
# <a name="financial-reconciliation-in-retail-stores"></a>Uzgodnienie finansowe w sklepach detalicznych

[!include [banner](includes/banner.md)]

W Microsoft Dynamics 365 Commerce w wersji 10.0.10 lub starszej funkcja, w której klient punktu sprzedaży (POS) obsługuje procesy na koniec dnia w sklepach internetowych pozwala pracownikom sklepów i kierownikom wykonywanie procesów końca dnia. Mogą to być na przykład deklaracje środków płatniczych, ukrycie raportu podczas zakończenia zmiany, uzgadnianie transakcji pomiędzy zmianami i zamykanie zmiany. Jednak w punkcie sprzedaży nie ma możliwości sfinalizowania informacji finansowych dotyczących zmiany, dzięki czemu można go użyć do zaksięgowania finansów w module Commerce Headquarter. Zazwyczaj menedżerowie sklepów są odpowiedzialni za wykonanie tego zadania. Aby umożliwić wylogowanie się ze zmiany, należy sprawdzić informacje, wprowadzić wymagane korekty i uzupełnić sumy dla tej zmiany. Ostateczne sumy powinny zostać zaksięgowane w modułach finansowych w Commerce Headquarter.

Ponadto w module Commerce w wersji 10.0.10 i starszych menedżerowie sklepów mogą przeglądać i dokonywać korekt wierszy wyciągów w module Commerce Headquarter. Jednak możliwość ta jest ograniczona, a kierownicy sklepów rzadko mają dostęp do klienta w module Commerce Headquarter. Ponadto analiza zestawień sprzedaży i dokonywanie korekt może być tylko wykonywane w przypadku tworzenia zestawień w module Commerce Headquarter. Proces ten jest jednak zazwyczaj procesem mającym miejsce w nocy. W związku z tym menedżerowie sklepów muszą czekać na zakończenie zmiany, gdyż to wtedy tworzone są zestawienia sprzedaży w module Commerce Headquarter.

W systemie Commerce w wersji 10.0.11 i nowszej menedżerowie sklepów mogą przeglądać, korygować i dokonywać zmian w samym kliencie punktu sprzedaży. Dane te następnie służą do tworzenia i księgowania sprawozdań finansowych w module Commerce Headquarter.

> [!NOTE]
> Funkcja związana z uzgadnianiem finansowym w sklepach sieci sprzedaży działa tylko wtedy, gdy włączona jest metoda tworzenia zamówień na podstawie cząstkowego kanału informacyjnego. Aby dowiedzieć się więcej, przejdź do [Tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach sieci sprzedaży](trickle-feed.md).

## <a name="set-up-financial-reconciliation"></a>Konfigurowanie uzgodnienia finansowego

Aby użyć funkcji uzgodnienia finansowego, należy wykonać następujące kroki.

1. W obszarze roboczym **Zarządzanie funkcjami** włącz funkcję **Wyciągi z sieci sprzedaży – cząstkowy kanał informacyjny**.
1. W profilu funkcji punktu sprzedaży dla odpowiedniego sklepu w polu ustaw opcję **Włącz opcję uzgodnienia finansowego w sklepie** na wartość **Tak**.

## <a name="more-information-about-financial-reconciliation"></a>Więcej informacji o uzgadnianiu finansowym

Po włączeniu funkcji uzgodnienia finansowego niektóre parametry zdefiniowane w skróconej karcie **Zestawienie/zamknięcie** na stronie **Sklepy detaliczne** w module Commerce Headquarter będą zsynchronizowane z bazą danych kanału. Przestregamy jest ten sam zbiór kryteriów obliczania i progów kwot, które są używane dla instrukcji sieci sprzedaży.

Po wywołaniu operacji **Zakończenia zmiany** system sprawdza, czy obliczone przez system kwoty i kwoty zadeklarowane kwoty. Jeśli się różnią, a różnica przekracza zdefiniowane progi, użytkownik jest otrzymuje komunikat i może wprowadzić wymagane korekty.

Korekty można wprowadzać dla każdej metody płatności. Po wybraniu metody płatności użytkownik może wyświetlać sumy dla różnych typów transakcji i edytować sumy dla określonego typu transakcji. Podczas edytowania system pokazuje oryginalną obliczoną kwotę i kwotę nadpisana dla danego typu transakcji. Użytkownik może również zapisywać notatki jako część procesu edycji. Notatki mogą być używane podczas inspekcji lub audytu.

Użytkownicy mogą ignorować monity i komunikaty sprawdzania poprawności i mogą przejść do zamknięcia zmiany. Jeśli jednak użytkownik zignoruje te monity, te same problemy zostaną ponownie utworzone po zakończeniu zmiany podczas księgowania zestawień finansowych w module Commerce Headquarters.

Operacja **Zamknięcia zmiany** w punkcie sprzedaży sprawdza również, czy wszystkie transakcje w bazie danych w trybie offline są synchronizowane z bazą danych kanału. Jeśli jakiekolwiek transakcje nie są zsynchronizowane, użytkownik otrzymuje komunikat ostrzegawczy, ponieważ sytuacja taka może spowodować nieprawidłowe przekroczenie kwot systemowych. W takiej sytuacji użytkownik może zakończyć operację **Zamknięcia zmiany** i spróbować zsynchronizować transakcje offline z bazą danych kanału. Użytkownik może również ręcznie skorygować wartości obliczone przez system w celu uwzględnienia transakcji, które nie są synchronizowane, dzięki czemu jest możliwe sfinalizowanie i zaksięgowanie odpowiedniego zbioru wyników finansowych. 

Jeśli jest używane księgowanie cząstkowych zestawień źródeł danych, dzięki czemu księgowanie transakcji jest oddzielone od księgowania finansów, można wybrać opcję korekty obliczonych przez system kwot dla brakujących transakcji w trybie offline. W ten sposób można upewnić się, że finanse są zawsze poprawnie księgowane i zapisane, niezależnie od brakujących transakcji. Transakcje offline można synchronizować z bazą danych kanału i modułem Commerce Headquarters, a następnie księgować je później niezależnie od księgowań finansowych.

Szczegóły związane z uzgodnieniem finansowym dla zmiany są zsynchronizowane z modułem Commerce Headquarters za pomocą zadania ściągania.

Sprawozdania finansowe sieci sprzedaży w module Commerce Headquarters nie obliczają sum, aby móc pokazać szczegóły w wierszach wyciągu. Zamiast tego używane są ostateczne kwoty w kliencie punktu sprzedaży do tworzenia i księgowania sprawozdań finansowych w module detalicznym.


[!INCLUDE[footer-include](../includes/footer-banner.md)]