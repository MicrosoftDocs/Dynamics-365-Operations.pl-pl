---
title: "Konfigurowanie opcji przetwarzania zamówień"
description: "Ten temat zawiera informacje dotyczące sposobu przetwarzania zamówień dla biur obsługi przy użyciu modułu Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 144bee2102b8d1901d1b4964f6c92501c1cd573d
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-order-processing-options"></a>Konfigurowanie opcji przetwarzania zamówień

[!include[banner](includes/banner.md)]


Ten temat zawiera informacje dotyczące sposobu przetwarzania zamówień dla biur obsługi przy użyciu modułu Microsoft Dynamics 365 for Retail. 

Moduł Handel detaliczny obsługuje wiele kanałów sieci sprzedaży, takich jak sklepy internetowe, sklepy tradycyjne i biura obsługi. W biurach obsługi, pracownicy zbierają zamówienia odbiorców przez telefon i tworzą zamówienia sprzedaży. W tym temacie opisano sposób tworzenia biura obsługi i konfigurowania opcji biura obsługi. Każde biuro obsługi może mieć własnych użytkowników, metody płatności, grupy cenowe, wymiary finansowe oraz metody dostawy. Opcje te można konfigurować podczas tworzenia biura obsługi. **Ważne:** zanim będzie można używać przepływów pracy biura obsługi podczas tworzenia zamówień sprzedaży przez użytkownika, użytkownik musi być przypisany do centrum obsługi jako jego użytkownik. Na stronie **Biuro obsługi** również można użyć w celu włączenia lub wyłączenia grup funkcji, które są unikatowe dla biur obsługi. Można włączyć następujące grupy funkcji:

-   **Kończenie zamówienia** — Ta grupa zawiera funkcje, które odnoszą się do płatności i kończenia zamówienia na stronie **Zamówienie sprzedaży**.
-   **Sprzedaż sterowana** — Ta grupa zawiera funkcje, które są powiązane z kodami źródłowymi, skryptami i żądaniami katalogu.

Jeśli włączysz te funkcje w ustawieniach biura obsługi, są one dostępne na stronie **Zamówienie sprzedaży** dla użytkowników, którzy są skojarzeni z biurem obsługi. Większość tych funkcji wymaga dodatkowych ustawień przed użyciem. Obrazy i skrypty są włączane jako część ustawień sprzedaży kierowanej dla określonego biura obsługi. Włączenie tych funkcji powoduje wyświetlanie skryptów i obrazów produktów w okienku pola informacji na stronie **zamówienia sprzedaży**. Zostanie wyświetlony domyślny ustawiony obraz produktu. Skrypty można skonfigurować dla towaru, katalogu, odbiorcy lub towaru w kontekście katalogu. Zamówienia biura obsługi mogą zawierać dodatkowe informacje o pochodzeniu ceny dla określonego wiersza zamówienia. Na przykład zamówienia mogą pokazywać zastosowane rabaty. Tę funkcję można włączyć w oknie **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami** &gt; **Ceny** &gt; **Szczegóły ceny**. Stronę **Szczegóły ceny** można otworzyć z listy rozwijanej **wiersza zamówienia sprzedaży**. Śledzenie zdarzeń zamówienia służy do celów inspekcji, dla porównywania podejmowanych akcji z zamówieniem w cyklu życia zamówienia lub do śledzenia akcji danego użytkownika. Na przykład można rejestrować działanie przy każdym tworzeniu zamówienia sprzedaży, wprowadzania blokady na zamówienie, zastąpieniu opłaty lub aktualizacji wiersza zamówienia przez użytkownika. Zdarzenia zamówienia można tak skonfigurować, aby śledzić akcje dla określonych użytkowników, grup użytkowników lub wszystkich użytkownikom w danym okresie czasu. Można wyświetlić czynności wykonane na dokumencie otwierając stronę **Zdarzenia zamówienia** z Okienka akcji na stronie określonego dokumentu. Zdarzenia zamówienia można skonfigurować w oknie **Sprzedaż i marketing** &gt; **Ustawienia** &gt; **Zdarzenia** &gt; **Zdarzenia zamówienia**. Gdy zamówienie odbiorcy nie może zostać wysyłane na czas, firma można automatycznie wysłać wiadomość e-mail z powiadomieniem do odbiorcy, aby wyjaśnić stan zamówienia i dać odbiorcy możliwość anulowania zamówienia. Jeśli opóźnienie wykracza poza określony próg, można automatycznie anulować zamówienia. Maksymalnie trzy wiadomości e-mail można wysłać w określonych odstępach czasu:

1.  **Pierwsze powiadomienie o anulowaniu** — odbiorca może zdecydować o anulowaniu zamówienia.
2.  **Drugie powiadomienie o anulowaniu** — odbiorca może zdecydować o anulowaniu zamówienia.
3.  **Końcowe powiadomienie o anulowaniu** — system anuluje zamówienie, a odbiorca zostanie poinformowany o anulowaniu.

Można zwolnić poszczególnych odbiorców i produkty z procesu automatycznego powiadamiania i anulowania. Podczas dodawania towaru do zamówienia wyzwalany jest alert dotyczący marży. Alert zawiera ważne informacje dotyczące towaru z uwzględnieniem rentowności marży cenowej i towarów. Dzięki tym informacjom można zdecydować, czy zastąpienie ceny jest odpowiednie podczas dodawania towaru do zamówienia sprzedaży. Można na przykład skonfigurować progi dla marż handlowych i określić, że progu 40% lub więcej powyżej kosztów można użyć dla danego towaru, ale próg 20 do 39% powyżej kosztów budzi wątpliwości. W takim przypadku każdy towar z progiem od 20 do 39 procent powoduje wyświetlenie ostrzeżenia. Towarów z progiem poniżej 20% powyżej kosztu nie można sprzedać, a cena towaru nie może być korygowana. Alerty dotyczące marży można skonfigurować w oknie **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami** &gt; **Alerty dotyczące marży**. Podczas konfigurowania przypisywania podatku na podstawie reguł domyślnych, można określić priorytet uzgadniania elementów adresu. Na przykład można określić, czy uzgadnianie grupy podatków według kodu pocztowego ma wyższy priorytet niż uzgadnianie grupy podatków według województwa. Podczas wprowadzania nowych rekordów adresu odbiorcy, grupa podatku jest automatycznie przypisywana, w zależności od zgodności adresu odbiorcy z domyślnymi regułami i ustawień priorytetu uzgadniania. Tę funkcję można skonfigurować na stronie **Parametry księgi głównej**.




