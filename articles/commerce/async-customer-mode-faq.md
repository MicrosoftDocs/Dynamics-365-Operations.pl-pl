---
title: Asynchroniczny tryb tworzenia klientów — Często zadawane pytania
description: Ten artykuł zawiera odpowiedzi na często zadawane pytania dotyczące trybu asynchronicznego tworzenia klientów w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 64c895fb9f3e55f7680759fa72626be6660aa67c
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690210"
---
# <a name="asynchronous-customer-creation-mode-faq"></a>Asynchroniczny tryb tworzenia klientów — Często zadawane pytania

[!include [banner](includes/banner.md)]

Ten artykuł zawiera odpowiedzi na często zadawane pytania dotyczące trybu asynchronicznego (async) tworzenia klientów w Microsoft Dynamics 365 Commerce.

### <a name="why-cant-i-enable-the-enable-editing-customers-in-asynchronous-mode-feature"></a>Dlaczego nie można włączyć funkcji „Włącz edytowanie odbiorców w trybie asynchronicznym"?

Przed włączeniem funkcji **Włącz edytowanie odbiorców w trybie asynchronicznym**, należy włączyć następujące funkcje:

- Usprawnienia wydajności zamówień odbiorcy i transakcji odbiorcy
- Włącz rozszerzone tworzenie odbiorcy asynchronicznego
- Włączanie tworzenia asynchronicznego dla adresów odbiorcy

### <a name="why-do-i-still-see-real-time-service-calls-made-to-commerce-headquarters-after-the-enable-editing-customers-in-asynchronous-mode-feature-is-enabled"></a>Dlaczego nadal są odbierane wywołania usługi Real-time Service wykonywane w centrali Commerce headquarters po włączeniu funkcji „Włącz edytowanie odbiorców w trybie asynchronicznym"?

Ten problem występuje, gdy nie zostały uruchomione zadania Commerce Data Exchange (CDX), aby zagwarantować, że stan funkcji i inne metadane kanału zostały zsynchronizowane z kanałem. Przed ponowieniem próby wykonania scenariusza upewnij się, że w programie Commerce Headquarters zostały uruchomione następujące zadania usługi CDX:

- 1110 (Konfiguracja globalna)
- 1010 (Odbiorcy)
- 1070 (Konfiguracja kanału)

Dane, które są buforowane w Commerce Scale Unit (CSU) mogą nie być natychmiast odzwierciedlane w centrali Commerce headquarters po uruchomieniu zadań CDX.

### <a name="why-doesnt-commerce-headquarters-show-customer-creation-or-updates-from-the-point-of-sale-pos-or-e-commerce-channel"></a>Dlaczego w centrali Commerce Headquarters nie są wyświetlane informacje dotyczące tworzenia lub aktualizacji punkt sprzedaży odbiorcy z programu punkt sprzedaży (POS) lub kanału e-commerce?

Upewnij się, że następujące akcje zostały wykonane w kolejności, w podanej kolejności.

1. Uruchom zadanie CDX P w programie Commerce Headquarters, aby zapewnić, że asynchroniczne dane klienta są przechowywane w tabelach **RETAILASYNCCUSTOMERV2**, **RETAILASYNCADDRESSV2**, **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** i **RETAILASYNCCUSTOMERATTRIBUTEV2**.
1. Uruchom zadanie wsadowe **synchronizowania odbiorców i żądań** kanałów w programie Commerce Headquarters. Po pomyślnym wykonaniu zadania wsadowego wszystkie rekordy, które zostały pomyślnie przetworzone z wcześniej wymienionych tabel, będą mieć w polu **OnlineOperationCompleted** wartość **1**.

### <a name="how-do-i-know-which-customer-management-in-asynchronous-mode-operation-has-failed-and-how-do-i-make-changes-if-they-are-required"></a>Jak sprawdzić, która operacja zarządzania klientami w trybie asynchronicznym zakończyła się niepowodzeniem, i jak wprowadzić zmiany, jeśli są one wymagane?

Aby wyświetlić wszystkie operacje w trybie asynchronicznym oraz ich stan synchronizacji, w programie Commerce Headquarters przejdź do pozycji **Handel detaliczny i inny \> Klienci \> Stan synchronizacji klienta**. Aby wprowadzić zmiany, edytuj określoną operację, zaktualizuj pola, wybierz przycisk **Zapisz**, a następnie wybierz opcję **Synchronizuj** w celu zsynchronizowania zmian.

