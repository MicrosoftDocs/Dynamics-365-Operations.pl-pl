---
title: Zarządzanie kredytem odbiorcy
description: ''
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 11da8b7fb59bc8f3e2568ada27db753cc815b9c2
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015353"
---
# <a name="customer-credit-management-overview"></a>Omówienie zarządzania kredytem odbiorcy

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Zarządzanie kredytami odbiorców umożliwia zarządzanie limitami kredytowymi i sterowanie przepływem zamówień sprzedaży za pomocą procesu księgowania na podstawie utworzonych reguł dotyczących kredytu. 

Proces zarządzania kredytami może obejmować niektóre albo wszystkie następujące kroki:
- Aktualizacja atrybutów kredytu odbiorcom w celu dostarczenia dodatkowych informacji o zdolnościach kredytowych 
- Umożliwia tworzenie limitów kredytu dla odbiorców przy użyciu korekt limitu kredytu
- Tworzenie tymczasowych limitów kredytu dla odbiorców używających korekt limitu kredytu w przypadku, gdy limit kredytu ma być tymczasowo zwiększany lub zmniejszany na podstawie potrzeb biznesowych
- Umożliwia dodanie dodatkowych informacji, które mogą mieć wpływ na limit kredytu, np. Informacje o ubezpieczeniach i gwarancjach
- Należy utworzyć grupy kredytowe odbiorcy łączące klientów, tak aby mogli oni korzystać z jednego limitu kredytowego
- Przypisz do odbiorców wyniki ryzyka, a następnie skorzystaj z tych wyników, aby automatycznie wygenerować limity kredytowe dla tych odbiorców za pomocą korekt limitu kredytu
- Utwórz reguły blokowania, które powodują wstrzymanie zamówienia podczas jednego lub większej liczby procesów księgowania, na podstawie czynników takich jak ryzyko, warunki płatności, limity kredytu, kwoty zaległe oraz procent wykorzystania limitu kredytu
- Umożliwia zarządzanie listą wstrzymanych zamówień sprzedaży, przeglądanie przyczyn wstrzymania i łagodzenie problemów
- Zwolnij zamówienia sprzedaży, aby były przetwarzane dalej w procesie księgowania
- Skonfiguruj przepływ pracy, aby zarządzać zatwierdzaniem zmian limitu kredytu i zwalnianiem zamówień sprzedaży


<a name="additional-resources"></a>Dodatkowe zasoby
--------
[Ustawienia parametrów modułu Zarządzanie kredytami odbiorcy](./cm-credit-mgmt-setup.md)

[Ustawienia informacji modułu Zarządzanie kredytami odbiorcy](./cm-setup-information.md)

[Dodaj informacje dotyczące zarządzania kredytem odbiorcy](./cm-add-credit-mgmt-information-customer.md)

[Grupy kredytowe odbiorcy](./cm-customer-credit-groups.md)

[Korekty limitu kredytu odbiorcy](./cm-credit-limit-adjustments.md)

[Obsługa wstrzymania kredytu zamówień sprzedaży](./cm-sales-order-credit-holds.md)

[Zadania okresowe zarządzania kredytami odbiorcy](./cm-periodic-tasks.md)


