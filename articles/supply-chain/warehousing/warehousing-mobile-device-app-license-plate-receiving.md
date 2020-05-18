---
title: Odbieranie numerów identyfikacyjnych za pomocą aplikacji magazynowej
description: W tym temacie opisano sposób konfigurowania aplikacji magazynowej w celu obsługi procesu odbierania numerów identyfikacyjnych przy użyciu numeru identyfikacyjnego do otrzymywania zapasu fizycznego.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 7d5ac6598ab80ece0164d7c92f5d84e91d21b385
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346383"
---
# <a name="license-plate-receiving-via-the-warehousing-app"></a>Odbieranie numerów identyfikacyjnych za pomocą aplikacji magazynowej

W tym temacie opisano sposób konfigurowania aplikacji magazynowej w celu obsługi procesu odbierania numerów identyfikacyjnych przy użyciu numeru identyfikacyjnego do otrzymywania zapasu fizycznego.

Ta funkcja służy do szybkiego rejestrowania przyjęcia przychodzącego zapasu, który jest powiązany z zawiadomieniem o zaliczce na poczet wysyłki (ASN). System automatycznie tworzy ASN, gdy procesy zarządzania magazynem służą do wysłania zamówienia przeniesienia. W procesie zamówienia zakupu można ręcznie zarejestrować ASN lub można go zaimportować automatycznie za pomocą procesu przychodzącej jednostki danych ASN.

Dane ASN są połączone z ładowaniem i wysyłkami za pośrednictwem *struktur pakowania*, w których palety (nadrzędne numery identyfikacyjne) mogą zawierać sprawy (zagnieżdżone numery identyfikacyjne).

> [!NOTE]
> Aby zmniejszyć liczbę transakcji magazynowych, gdy używane są struktury opakowań z zagnieżdżonymi numerami identyfikacyjnymi, system rejestruje fizycznie dostępne zapasy na nadrzędnym numerze identyfikacyjnym. Aby wyzwolić przesunięcie fizycznego stanu zapasów z nadrzędnego numeru identyfikacyjnego do zagnieżdżoneego numeru identyfikacyjnego na podstawie danych o strukturze pakowania, urządzenie przenośne musi dostarczyć element menu, który jest oparty procesie tworzenia pracy *Pakowanie do zagnieżdżonych numerów identyfikacyjnych*.

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a>Wyświetlanie lub pomijanie strony Podsumowanie przyjęcia

Funkcji *Kontroluj, czy wyświetlać stronę podsumowania odbioru na urządzeniach mobilnych* można użyć w celu wykorzystania dodatkowego przepływu aplikacji magazynowej w ramach procesu odbierania numerów identyfikacyjnych.

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Kontroluj, czy wyświetlać stronę podsumowania odbioru na urządzeniach mobilnych*

Gdy ta funkcja jest włączona, pozycje menu urządzenia mobilnego dotyczące odbioru i odłożenia tablicy rejestracyjnej oraz odłożenia tablicy rejestracyjnej będą zapewniać ustawienie **Wyświetl stronę podsumowania przyjęcia**. To ustawienie ma następujące opcje:

- **Wyświetlenie szczegółowego podsumowania** — podczas przyjmowania numeru identyfikacyjnego pracownicy będą widzieć dodatkową stronę, na której są wyświetlane pełne informacje dotyczące ASN.
- **Pomiń podsumowanie** — pracownicy nie będą widzieli pełnych informacji ASN. Pracownicy magazynu również nie będą mogli ustawić kodu dyspozycji ani dodać wyjątków podczas procesu odbioru.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy

Nie można użyć procesu odbierania numeru identyfikacyjnego, jeśli numer ASN zawiera identyfikator numeru identyfikacyjnego, który już istnieje, i zawiera fizyczne dostępne dane w lokalizacji magazynowej innej niż lokalizacja magazynu, w którym występuje rejestracja numeru identyfikacyjnego.

W scenariuszach zamówień przeniesienia, w których magazyn tranzytowy nie śledzi numerów identyfikacyjnych (a zatem nie śledzi fizycznych dostępnych zapasów powiązanych z numerem identyfikacyjnym), można użyć funkcji *Zapobiegaj wykorzystywaniu wysłanych numerów identyfikacyjnych z zamówień przeniesienia w magazynach innych niż magazyn docelowy* w celu uniemożliwienia fizycznej aktualizacji numerów identyfikacyjnych w tranzycie.

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy*

Aby zarządzać funkcjami, gdy ta funkcja jest dostępna, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Ogólne**, na skróconej karcie **Numery identyfikacyjne** w polu **Zasady dotyczące numerów identyfikacyjnych magazynu tranzytowego** określ jedną z następujących wartości:

    - **Zezwalaj na ponowne użycie nieśledzonego numeru identyfikacyjnego** — system działa tak samo, jak działa, gdy funkcja *Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy* nie jest dostępna. Ta wartość jest ustawieniem domyślnym przy pierwszej aktywacji funkcji.
    - **Zapobiegaj ponownemu użyciu nieśledzonych numerów identyfikacyjnych** — w magazynie docelowym będą dozwolone tylko aktualizacje stanu zapasów związane ze wysyłką numeru identyfikacyjnego, dopóki zamówienie przeniesienia nie zostanie odebrane.

## <a name="more-information"></a>Więcej informacji

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

Aby uzyskać więcej informacji o elementach menu urządzeń przenośnych, zapoznaj się z tematem [Konfigurowanie urządzeń przenośnych do pracy magazynowej](configure-mobile-devices-warehouse.md).
