---
title: Zarządzanie zapasami w sklepie
description: W tym temacie opisano typy dokumentów, których można używać do zarządzania zapasami.
author: rubencdelgado
manager: AnnBe
ms.date: 01/18/2019
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
ms.openlocfilehash: 02f8afbe3bb6f94c66a8b5aa02531c219adc3963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "339241"
---
# <a name="store-inventory-management"></a>Zarządzanie zapasami w sklepie

[!include [banner](includes/banner.md)]

W tym temacie opisano typy dokumentów, których można używać do zarządzania zapasami.

Następujące typy dokumentów służą do zarządzania zapasami w organizacji.

Podczas pracy z zapasami w programie Dynamics 365 for Retail i używania aplikacji POS należy zwrócić uwagę, że POS zapewnia ograniczoną obsługę wymiarów magazynowych i zapasów określonych typów towarów.  

Rozwiązanie POS nie obsługuje następujących konfiguracje towarów:
- Towary BOM (z wyjątkiem zestawów wykorzystujących komponenty struktury BOM)
- Towary w ilości efektywnej
- Towary wchodzące w skład partii

Aplikacja POS aktualnie nie obsługuje następujących wymiarów śledzenia w POS:
- Wymiar śledzenia partii
- Wymiar właściciela

Rozwiązanie POS zapewnia ograniczoną obsługę następujących wymiarów. Ograniczona obsługa oznacza, że POS może w sposób automatyczny domyślnie używać niektórych z tych wymiarów w transakcjach zapasów na podstawie konfiguracji magazynu/sklepu. POS nie obsługuje w pełni wymiarów w sposób, w jaki są one obsługiwane, jeśli transakcja sprzedaży jest ręcznie wprowadzana do systemu ERP. 

- Lokalizacja
- Numer identyfikacyjny (stosowany tylko po włączeniu opcji **Używaj procesu zarządzania magazynem** dla towaru i magazynu sklepu)
- Numer seryjny
- Stan zapasów

> [!NOTE]
> Wszystkie organizacje muszą przetestować konfiguracje towarów za pomocą POS w środowiskach rozwojowych lub testowych przed ich wdrożeniem do produkcji. Należy przetestować towary, wykonując zwykłą sprzedaż kasową i tworząc zamówienia odbiorcy (jeśli dotyczy) za pomocą POS z Twoimi towarami. Testowanie musi obejmować procesy księgowania pełnych zestawień w środowisku testowym i sprawdzenie, że nie ma problemów.
> Konfigurowanie towarów w sposób, który nie jest obsługiwany przez aplikację POS, bez odpowiedniego przetestowania, może doprowadzić do błędu przetwarzania księgowania zestawienia w produkcji, którego nie będzie można łatwo naprawić. Zmiany wprowadzone w aplikacji przez partnera lub klienta mogą opcjonalnie zezwalać na pomyślne realizowanie tych procesów księgowania. Jeśli dostosowania nie są potrzebne, organizacja musi upewnić się, że konfiguracja produktu została wykonane w sposób, który jest obsługiwany przez standardowe proces aplikacji POS/tworzenia zamówień/księgowania zestawień.

## <a name="purchase-orders"></a>Zamówienia zakupu

Zamówienia zakupu są tworzone w centrali. Jeśli magazyn sprzedaży detalicznej znajduje się w nagłówku zamówienia zakupu, zamówienia można otrzymać w sklepie przy użyciu aplikacji Modern POS (MPOS) lub Cloud POS dostępnej w programie Microsoft Dynamics 365 for Retail Po wprowadzeniu ilości, które są odbierane w sklepie, można je zapisać lokalnie i modyfikować. Można też zatwierdzić ilości i wysłać do centrali. Zlokalizowane w centrali ilości, które zostały odebrane w sklepie, są wyświetlane w programie Dynamics 365 for Retail w polu **Odbierz teraz** na zamówieniu zakupu.

## <a name="transfer-orders"></a>Zamówienia przeniesienia

W zleceniu przesunięcia można określić, że dany sklep jest lokalizacją, z której można wysyłać towary. W takim przypadku zamówienie przeniesienia jest wyświetlane w sklepie jako żądanie pobrania w aplikacji MPOS lub Cloud POS. Po pobraniu żądanych ilości zostaną one zatwierdzone i przesłane do centrali. Zlokalizowane w centrali ilości, które zostały odebrane w sklepie, są wyświetlane w programie Dynamics 365 for Retail w polu **Wyślij teraz** na zamówieniu przeniesienia. W zleceniu przesunięcia można określić, że dany sklep jest lokalizacją, do której można wysyłać towary. W takim przypadku zamówienie przeniesienia jest wyświetlane w sklepie jako żądanie przyjęcia w aplikacji MPOS lub Cloud POS. Po wprowadzeniu ilości, które są odbierane w sklepie, można je zapisać lokalnie i modyfikować. Można też zatwierdzić ilości i wysłać do centrali. Zlokalizowane w centrali ilości, które zostały odebrane w sklepie, są wyświetlane w programie Dynamics 365 for Retail w polu **Odbierz teraz** na zamówieniu przeniesienia.

## <a name="stock-counts"></a>Stany zapasów z inwentaryzacji

Inwentaryzacje mogą być zaplanowane lub niezaplanowane. Zaplanowana inwentaryzacja jest inicjowana z poziomu centrali, która określa towary podlegające inwentaryzacji. Centrala tworzy dokument inwentaryzacji, który można otrzymać w sklepie. Rzeczywista ilość dostępnych zapasów jest wprowadzana w aplikacji MPOS lub Cloud POS. Niezaplanowane inwentaryzacje są inicjowane w sklepie, a rzeczywista ilość dostępnych zapasów jest aktualizowana w aplikacji MPOS lub Cloud POS. W odróżnieniu od zaplanowanej inwentaryzacji niezaplanowana nie ma wstępnie zdefiniowanej listy pozycji. Po zakończeniu inwentaryzacja dowolnego typu jest zatwierdzana wysyłana do centrali. W centrali dane podlegają sprawdzeniu i zaksięgowaniu.

## <a name="inventory-lookup"></a>Wyszukiwanie w magazynie

Bieżącą ilość produktów dostępnych w wielu sklepach i magazynach można obejrzeć na stronie Wyszukiwanie w magazynie. Oprócz bieżącej ilości dostępnej w zapasach można wyświetlić przyszłe dostępności zapasów (ATP) dla poszczególnych sklepów. Aby to zrobić, zaznacz sklep, dla którego chcesz obejrzeć ATP, i kliknij przycisk **Pokaż dostępność sklepu**.
