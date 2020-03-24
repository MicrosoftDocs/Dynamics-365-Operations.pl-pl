---
title: Zarządzanie kredytem odbiorcy
description: Zarządzanie kredytami odbiorców umożliwia zarządzanie limitami kredytowymi i sterowanie przepływem zamówień sprzedaży za pomocą procesu księgowania na podstawie utworzonych reguł dotyczących kredytu.
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
ms.openlocfilehash: 1e7d3325587d7cfc876e8f8c7b9207d44046ccd4
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124284"
---
# <a name="customer-credit-management-overview"></a>Omówienie zarządzania kredytem odbiorcy

[!include [banner](../includes/banner.md)]

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


