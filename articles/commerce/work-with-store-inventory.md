---
title: Zarządzanie zapasami w sklepie
description: W tym temacie opisano typy dokumentów, których można używać do zarządzania zapasami.
author: rubencdelgado
manager: AnnBe
ms.date: 04/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 3f7f228bbf312a2ccdc96d3e95287898bee01de4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023646"
---
# <a name="store-inventory-management"></a>Zarządzanie zapasami w sklepie

[!include [banner](includes/banner.md)]

Podczas pracy z zapasami w programie Dynamics 365 Commerce i używania aplikacji POS należy zwrócić uwagę, że POS zapewnia ograniczoną obsługę wymiarów magazynowych i zapasów określonych typów towarów.

Rozwiązanie POS nie obsługuje następujących konfiguracje towarów:

- Towary BOM (z wyjątkiem zestawów wykorzystujących komponenty struktury BOM)
- Towary w ilości efektywnej
- Towary wchodzące w skład partii

Aplikacja POS aktualnie nie obsługuje następujących wymiarów śledzenia w POS:

- Wymiar śledzenia partii
- Wymiar właściciela

Rozwiązanie POS zapewnia ograniczoną obsługę następujących wymiarów. Ograniczona obsługa oznacza, że POS może w sposób automatyczny domyślnie używać niektórych z tych wymiarów w transakcjach zapasów na podstawie konfiguracji magazynu/sklepu. POS nie obsługuje w pełni wymiarów w sposób, w jaki są one obsługiwane, jeśli transakcja sprzedaży jest ręcznie wprowadzana do systemu ERP. 

- **Lokalizacja magazynu** — użytkownicy nie będą mieli możliwości zarządzania lokalizacją magazynu przyjmującego dla towarów otrzymanych w magazynie sklepu, jeśli sklep nie został skonfigurowany pod kątem korzystania z procesu zarządzania magazynem. Dla tych towarów będą używane domyślne lokalizacje przyjęcia zdefiniowane w magazynie sklepu. Jeśli dla sklepu został włączony proces zarządzania magazynem, zostanie wyzwolony monit o wybranie lokalizacji odbierającej dla całego paragonu. Towary sprzedane ze sklepu będą zawsze sprzedawane poza domyślną lokalizacją zgodnie z ustawieniami magazynu sklepu. Lokalizacja zarządzania zapasami zwrotu może być kontrolowana za pośrednictwem domyślnej definicji lokalizacji zwrotu w magazynie sklepu lub na podstawie kodów przyczyn zwrotu, zgodnie z zasadami lokalizacji zwrotu.
- **Numer identyfikacyjny** — stosowany tylko po włączeniu opcji **Używaj procesu zarządzania magazynem** dla towaru i magazynu sklepu. W punkcie sprzedaży, w przypadku przyjęcia zapasów do magazynu sklepu, w którym został włączony proces zarządzania magazynem, a lokalizacja wybrana do odebrania towaru jest powiązana z profilem lokalizacji, który wymaga kontroli numeru identyfikacyjnego, aplikacja punktu sprzedaży będzie systematycznie stosować numer identyfikacyjny do wiersza przyjęcia. Użytkownicy w punkcie sprzedaży nie będą mieli możliwości zmiany tego numeru identyfikacyjnego ani zarządzania nim. Jeśli wymagane jest pełne zarządzanie numerami identyfikacyjnymi, zaleca się, aby w sklepie można było zarządzać odbiorem tych towarów za pomocą aplikacji mobilnej WMS lub klienta zaplecza Office ERP
- **Numer seryjny** — aplikacja punktu sprzedaży ma ograniczone funkcje obsługi dla pojedynczego numeru seryjnego, który ma być zarejestrowany w wierszu sprzedaży transakcji dla zamówień utworzonych w punkcie sprzedaży z towarami seryjnymi. Ten numer seryjny nie jest sprawdzany względem zarejestrowanych numerów seryjnych, które już są w magazynie. Jeśli zamówienie sprzedaży jest tworzone w kanale biura obsługi lub realizowane za pośrednictwem systemu ERP, a wiele numerów seryjnych jest zarejestrowanych w jednym wierszu sprzedaży w trakcie procesu realizacji w systemie ERP, te numery seryjne nie będą mogły zostać zastosowane ani sprawdzone, jeśli zwrot ma wartość „przetworzono” w punkcie sprzedaży dla tych zamówień.
- **Stan zapasów** — w przypadku towarów, które korzystają z procesu zarządzania magazynem i wymagają stanu zapasów, to pole stanu nie może być konfigurowane ani modyfikowane za pośrednictwem aplikacji punktu sprzedaży. Domyślny stan zapasów określony w konfiguracji magazynu sklepu będzie używany podczas przyjęcia towarów do magazynu.

> [!NOTE]
> Wszystkie organizacje muszą przetestować konfiguracje towarów za pomocą POS w środowiskach rozwojowych lub testowych przed ich wdrożeniem do produkcji. Należy przetestować towary, wykonując zwykłą sprzedaż kasową i tworząc zamówienia odbiorcy (jeśli dotyczy) za pomocą POS z Twoimi towarami. Testowanie musi obejmować procesy księgowania pełnych zestawień w środowisku testowym i sprawdzenie, że nie ma problemów.
>
> Konfigurowanie towarów w sposób, który nie jest obsługiwany przez aplikację POS, bez odpowiedniego przetestowania, może doprowadzić do błędu przetwarzania księgowania zestawienia w produkcji, którego nie będzie można łatwo naprawić. Zmiany wprowadzone w aplikacji przez partnera lub klienta mogą opcjonalnie zezwalać na pomyślne realizowanie tych procesów księgowania. Jeśli dostosowania nie są potrzebne, organizacja musi upewnić się, że konfiguracja produktu została wykonane w sposób, który jest obsługiwany przez standardowe proces aplikacji POS/tworzenia zamówień/księgowania zestawień.

## <a name="purchase-orders"></a>Zamówienia zakupu

Zamówienia zakupu są tworzone w centrali. Jeśli magazyn znajduje się w nagłówku zamówienia zakupu, zamówienia można otrzymać w sklepie przy użyciu aplikacji Modern POS (MPOS) lub Cloud POS dostępnej w programie , korzystając z operacji **pobrania/przyjęcia**. Po wprowadzeniu ilości odebranych w sklepie w polu **Dostarczone teraz** w punkcie sprzedaży dla dokumentu zamówienia zakupu, można je zapisać lokalnie lub zatwierdzić. Zapisanie tych danych lokalnie nie ma wpływu na zapasy w magazynie. Zapisywanie powinno być wykonywane tylko wtedy, gdy użytkownik nie jest gotowy do zaksięgowania przyjęcia w centrali i musi mieć możliwość tymczasowego przechowywania poprzednio wprowadzonych danych towaru **dostarczonego teraz**. Spowoduje to zapisanie lokalne danych towaru dostarczonego teraz w bazie danych kanału użytkownika. Po przetworzeniu dokumentu przy użyciu opcji **zatwierdzania** dane towaru **dostarczonego teraz** są wysyłane do centrali i zostanie zaksięgowany paragon zamówienia zakupu. 

## <a name="transfer-orders"></a>Zamówienia przeniesienia

Zamówienie przeniesienia może określać, czy dany sklep jest lokalizacją, z której można wysyłać towary, czy też lokalizacją, w której zostaną odebrane zapasy. Jeśli użytkownik punktu sprzedaży jest magazynem wysyłkowym dla zamówienia przeniesienia, będzie mógł wprowadzać ilości **wysyłki teraz** z punktu sprzedaży. Dane wprowadzone przez sklep wysyłkowy mogą być zapisywane lokalnie lub zatwierdzane. W przypadku zapisania danych lokalnie nie są wprowadzane żadne aktualizacje dokumentu zamówienia przeniesienia w centrali. Zapisywanie powinno być wykonywane tylko wtedy, gdy użytkownik nie jest gotowy do zaksięgowania wysyłki w centrali i musi mieć możliwość tymczasowego przechowywania poprzednio wprowadzonych danych towaru **wysłanego teraz**. Gdy sklep będzie gotowy do potwierdzenia wysyłki, należy wybrać opcję **Zatwierdź**. Spowoduje to zaksięgowanie wysyłki zamówienia przeniesienia w centrali, dzięki czemu magazyn odbierający będzie miał teraz możliwość otrzymywania towaru na podstawie tego dokumentu. 

Jeśli użytkownik punktu sprzedaży jest magazynem odbierającym dla zamówienia przeniesienia, będzie mógł wprowadzać ilości **dostarczone teraz** z punktu sprzedaży. Dane wprowadzone przez sklep odbierający mogą być zapisywane lokalnie lub zatwierdzane. Zapisywanie powinno być wykonywane tylko wtedy, gdy użytkownik nie jest gotowy do zaksięgowania przyjęcia w centrali i musi mieć możliwość tymczasowego przechowywania poprzednio wprowadzonych danych towaru **dostarczonego teraz**. Spowoduje to zapisanie lokalne danych towaru dostarczonego teraz w bazie danych kanału użytkownika. Po przetworzeniu dokumentu przy użyciu opcji **zatwierdzania** dane towaru **dostarczonego teraz** są wysyłane do centrali i zostanie zaksięgowany paragon zamówienia przeniesienia. Należy pamiętać, że sklep odbierający będzie mógł odebrać ilość mniejszą lub równą wysłanej ilości. Próba odbioru ilości z zamówienia przeniesienia, które nie zostały wysłane, spowoduje wyświetlenie komunikatu o błędzie, a paragon nie zostanie potwierdzony w centrali.

## <a name="stock-counts"></a>Stany zapasów z inwentaryzacji

Inwentaryzacje mogą być zaplanowane lub niezaplanowane. Zaplanowana inwentaryzacja jest inicjowana z poziomu centrali, która określa towary podlegające inwentaryzacji. Centrala tworzy dokument inwentaryzacji, który można otrzymać w sklepie. Rzeczywista ilość dostępnych zapasów jest wprowadzana w aplikacji MPOS lub Cloud POS. Niezaplanowane inwentaryzacje są inicjowane w sklepie, a rzeczywista ilość dostępnych zapasów jest aktualizowana w aplikacji MPOS lub Cloud POS. W odróżnieniu od zaplanowanej inwentaryzacji niezaplanowana nie ma wstępnie zdefiniowanej listy pozycji. Po zakończeniu inwentaryzacja dowolnego typu jest zatwierdzana wysyłana do centrali. W centrali dane podlegają sprawdzeniu i zaksięgowaniu w ramach osobnej procedury.

## <a name="inventory-lookup"></a>Wyszukiwanie w magazynie

Bieżącą ilość produktów dostępnych w wielu sklepach i magazynach można obejrzeć na stronie **Wyszukiwanie w magazynie**. Oprócz bieżącej ilości dostępnej w zapasach można wyświetlić przyszłe dostępności zapasów (ATP) dla poszczególnych sklepów. Aby to zrobić, zaznacz sklep, dla którego chcesz obejrzeć ATP, i kliknij przycisk **Pokaż dostępność sklepu**.
