---
title: Omówienie kredytów i windykacji
description: W tym temacie omówiono funkcje dotyczące kredytów i windykacji.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ade76b822904f49135e07dfe0a39d2227dd1dd77
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992995"
---
# <a name="credit-and-collections-overview"></a>Omówienie kredytów i windykacji

[!include [banner](../includes/banner.md)]

Można zarządzać limitami kredytowymi odbiorców i wykonywać działania windykacji, gdy staną się niezbędne.

## <a name="credit-management"></a>Zarządzanie kredytem

Zarządzanie kredytami odbiorców umożliwia zarządzanie limitami kredytowymi i sterowanie przepływem zamówień sprzedaży za pomocą procesu księgowania na podstawie utworzonych reguł dotyczących kredytu.

Proces zarządzania kredytami może obejmować następujące kroki:

- Aktualizacja atrybutów kredytu dla odbiorców w celu dostarczenia dodatkowych informacji o zdolnościach kredytowych.
- Umożliwia tworzenie limitów kredytu dla odbiorców przy użyciu korekt limitu kredytu.
- Umożliwia tymaczasowe tworzenie limitów kredytu dla odbiorców przy użyciu korekt limitu kredytu. W ten sposób można tymczasowo zwiększyć lub zmniejszyć limity kredytowe klientów na podstawie wymagań biznesowych.
- Umożliwia dodanie informacji, które mogą mieć wpływ na limit kredytu, np. Informacje o ubezpieczeniach i gwarancjach.
- Należy utworzyć grupy kredytowe odbiorcy łączące klientów, tak aby mogli oni korzystać z jednego limitu kredytowego.
- Przypisz do odbiorców wyniki ryzyka, a następnie skorzystaj z tych wyników, aby automatycznie wygenerować limity kredytowe dla tych odbiorców za pomocą korekt limitu kredytu.
- Utwórz reguły blokowania, które powodują wstrzymanie zamówienia podczas jednego lub większej liczby procesów księgowania, na podstawie czynników takich jak ryzyko, warunki płatności, limity kredytu, kwoty zaległe oraz procent wykorzystania limitu kredytu.
- Umożliwia zarządzanie listą wstrzymanych zamówień sprzedaży, przeglądanie przyczyn wstrzymania i łagodzenie problemów.
- Zwolnij zamówienia sprzedaży, aby były przetwarzane dalej w procesie księgowania.
- Skonfiguruj przepływ pracy, aby zarządzać zatwierdzaniem zmian limitu kredytu i zwalnianiem zamówień sprzedaży.

## <a name="collections-management"></a>Zarządzanie windykacjami

Informacje dotyczące windykacji w module Rozrachunki z odbiorcami są zarządzane w jednym centralnym widoku na stronie **Windykacje**. Kierownicy ds. windykacji i windykacji mogą używać tego centralnego widoku do zarządzania windykacją. Agenci ds. windykacji mogą rozpocząć proces windykacji na podstawie list odbiorców, które są generowane przy użyciu wstępnie zdefiniowanych kryteriów windykacji, lub ze strony **Odbiorcy**.

Przed rozpoczęciem konfigurowania lub pracy z windykacjami należy zapoznać się z następującymi pojęciami:

- Migawka wiekowania odbiorcy zawiera informacje o wiekowanym saldzie w określonym momencie.
- Pule klientów związanych z windykacjami pomagają w organizacji pracy.
- Agenci ds. windykacji mają własne pule klientów.
- Strony listy organizują odbiorców związanych z windykacjami, działania i sprawy.
- Wszystkie informacje o windykacji dotyczące danego odbiorcy znajdują się na jednej stronie, na której można podejmować wymagane działania.
- W jednym kroku można wykonać uchylenie, przywrócenie lub wycofanie odsetek.
- W jednym kroku można tworzyć transakcje odpisu.
- W jednym kroku można przetwarzać płatności przy niewystarczających funduszach.

Aby zapoznać się z opisami tych pojęć, zajrzyj do [Pojęcia kluczowe związane z zarządzaniem windykacją](./cm-collections-concepts.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Ustawienia parametrów modułu Zarządzanie kredytami odbiorcy](./cm-credit-mgmt-setup.md)

[Ustawienia informacji modułu Zarządzanie kredytami odbiorcy](./cm-setup-information.md)

[Dodaj informacje dotyczące zarządzania kredytem odbiorcy](./cm-add-credit-mgmt-information-customer.md)

[Grupy kredytowe odbiorcy](./cm-customer-credit-groups.md)

[Korekty limitu kredytu odbiorcy](./cm-credit-limit-adjustments.md)

[Obsługa wstrzymania kredytu zamówień sprzedaży](./cm-sales-order-credit-holds.md)

[Zadania okresowe zarządzania kredytami odbiorcy](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]