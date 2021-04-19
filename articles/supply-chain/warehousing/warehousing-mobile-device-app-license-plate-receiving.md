---
title: Numer identyfikacyjny odbierany za pomocą aplikacji mobilnej Zarządzanie magazynem
description: W tym temacie opisano sposób konfigurowania aplikacji mobilnej Warehouse Management w celu obsługi procesu odbierania numerów identyfikacyjnych przy użyciu numeru identyfikacyjnego do otrzymywania zapasu fizycznego.
author: perlynne
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 8c662da296bea7def443cb166bd3f7e501c9abcc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823198"
---
# <a name="license-plate-receiving-via-the-warehouse-management-mobile-app"></a>Numer identyfikacyjny odbierany za pomocą aplikacji mobilnej Zarządzanie magazynem

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania aplikacji mobilnej Warehouse Management w celu obsługi procesu odbierania numerów identyfikacyjnych przy użyciu numeru identyfikacyjnego do otrzymywania zapasu fizycznego.

Ta funkcja służy do szybkiego rejestrowania przyjęcia przychodzącego zapasu, który jest powiązany z zawiadomieniem o zaliczce na poczet wysyłki (ASN). System automatycznie tworzy ASN, gdy procesy zarządzania magazynem służą do wysłania zamówienia przeniesienia. W procesie zamówienia zakupu można ręcznie zarejestrować ASN lub można go zaimportować automatycznie za pomocą procesu przychodzącej jednostki danych ASN.

Dane ASN są połączone z ładowaniem i wysyłkami za pośrednictwem *struktur pakowania*, w których palety (nadrzędne numery identyfikacyjne) mogą zawierać sprawy (zagnieżdżone numery identyfikacyjne).

> [!NOTE]
> Aby zmniejszyć liczbę transakcji magazynowych, gdy używane są struktury opakowań z zagnieżdżonymi numerami identyfikacyjnymi, system rejestruje fizycznie dostępne zapasy na nadrzędnym numerze identyfikacyjnym. Aby wyzwolić przesunięcie fizycznego stanu zapasów z nadrzędnego numeru identyfikacyjnego do zagnieżdżoneego numeru identyfikacyjnego na podstawie danych o strukturze pakowania, urządzenie przenośne musi dostarczyć element menu, który jest oparty procesie tworzenia pracy *Pakowanie do zagnieżdżonych numerów identyfikacyjnych*.

## <a name="warehousing-mobile-device-app-processing"></a>Przetwarzanie aplikacji dla urządzenia przenośnego z Warehousing

Gdy pracownik skanuje przychodzący identyfikator numeru identyfikacyjnego, system inicjalizuje proces odbierania numerów identyfikacyjnych. Na podstawie tych informacji zawartość numeru identyfikacyjnego (danych pochodzących z ASN) jest fizycznie rejestrowana w lokalizacji doku rozładunkowego. Następujące przepływy będą uzależnione od potrzeb procesu biznesowego.

## <a name="work-policies"></a>Zasady pracy

Podobnie jak w przypadku (na przykład) proces *Zgłoszenie wyrobów gotowych* element menu urządzenia mobilnego, proces odbierania numerów identyfikacyjnych obsługuje kilka przepływów pracy w oparciu o zdefiniowaną konfigurację.

### <a name="work-policies-with-work-creation"></a>Zasady pracy z tworzeniem pracy

Podczas rejestrowania pozycji przychodzących przy użyciu zasady pracy, która tworzy pracę, system generuje i zapisuje rekordy pracy odłożenia dla każdej rejestracji. W przypadku korzystania z procesu pracy *Odbieranie numeru identyfikacyjnego i odłożenie* rejestracja i odkładanie jest obsługiwane jako pojedyncza operacja za pomocą jednego elementu menu urządzenia przenośnego. W przypadku korzystania z procesu *Przyjęcie numeru identyfikacyjnego* procesy przyjmowania i odkładania są traktowane jako dwie różne operacje magazynowe, każdy z własnymi elementami menu urządzeń przenośnych.

### <a name="work-policies-without-work-creation"></a>Zasady pracy bez tworzenia pracy

Proces odbierania numeru identyfikacyjnego można stosować bez tworzenia pracy. W przypadku zdefiniowania zasad pracy mających typ zlecenia pracy *Przyjęcie przeniesienia* lub *Zamówienia zakupu*, a następnie użycia procesu do *Odbieranie numeru identyfikacyjnego (i odłożenie)* na podstawie poniższych dwóch procesów aplikacji mobilnej Warehousing nie zostanie utworzona żadna praca. W zamian zarejestrują one po prostu przychodzące zapasy fizyczne na numerze identyfikacyjnym w doku przyjęcia przychodzącego.

- *Przyjęcie numeru identyfikacyjnego*
- *Odbieranie numeru identyfikacyjnego i odłożenie*

> [!NOTE]
> - W sekcji **Lokalizacje zapasów** należy zdefiniować co najmniej jedną lokalizację zasady pracy. Nie można określić tej samej lokalizacji dla wielu zasad pracy.
> - Opcja **Drukuj etykietę** dla elementów menu aplikacji Warehousing na urządzenia przenośne nie powoduje drukowania etykiety numeru identyfikacyjnego bez tworzenia pracy.

Aby udostępnić tę funkcję w systemie, należy włączyć funkcję *Ulepszenia odbierania numerów identyfikacyjnych* w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>Odbiór zapasów w lokalizacji, w której nie są śledzone numery identyfikacyjne

Istnieje możliwość użycia lokalizacji magazynowej przypisanej do profilu lokalizacji, nawet jeśli **Śledzenie numerów identyfikacyjnych** nie jest włączone. Dlatego po odebraniu zapasów można bezpośrednio zarejestrować dostępne zapasy w lokalizacji bez tworzenia pracy.

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>Dodaj elementy menu urządzeń przenośnych dla każdej lokalizacji przyjęcia w magazynie

Funkcja *Ulepszenia odbierania numerów identyfikacyjnych* pozwala uzyskać dostęp do każdej lokalizacji w magazynie, dodając do aplikacji mobilnej Warehousing specyficzne dla lokalizacji pozycje menu odbiór numeru identyfikacyjnego (i odkładania). Poprzednio system obsługiwał odbieranie tylko w lokalizacji domyślnej zdefiniowanej dla każdego magazynu. Jednak gdy ta funkcja jest włączona, elementy menu urządzenia mobilnego do odbierania (i odkładania) numerów identyfikacyjnych udostępniają teraz opcję **Użyj domyślnych danych**, która pozwala wybrać niestandardową lokalizację „do” dla każdego elementu menu. (Ta opcja jest już dostępna dla innych typów elementów menu.)

Aby udostępnić tę funkcję w systemie, należy włączyć funkcję *Ulepszenia odbierania numerów identyfikacyjnych* w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="show-or-skip-the-receiving-summary-page"></a>Wyświetlanie lub pomijanie strony Podsumowanie przyjęcia

Funkcji *Kontroluj, czy wyświetlać stronę podsumowania odbioru na urządzeniach mobilnych* można użyć w celu wykorzystania dodatkowego przepływu aplikacji Warehouse Management w ramach procesu odbierania numerów identyfikacyjnych.

Gdy ta funkcja jest włączona, pozycje menu urządzenia mobilnego dotyczące odbioru i odłożenia tablicy rejestracyjnej oraz odłożenia tablicy rejestracyjnej będą zapewniać ustawienie **Wyświetl stronę podsumowania przyjęcia**. To ustawienie ma następujące opcje:

- **Wyświetlenie szczegółowego podsumowania** — podczas przyjmowania numeru identyfikacyjnego pracownicy będą widzieć dodatkową stronę, na której są wyświetlane pełne informacje dotyczące ASN.
- **Pomiń podsumowanie** — pracownicy nie będą widzieli pełnych informacji ASN. Pracownicy magazynu również nie będą mogli ustawić kodu dyspozycji ani dodać wyjątków podczas procesu odbioru.

Aby udostępnić tę funkcję w systemie, należy włączyć *Kontroluj, czy wyświetlać stronę podsumowania odbioru na urządzeniach mobilnych* w [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy

Nie można użyć procesu odbierania numeru identyfikacyjnego, jeśli numer ASN zawiera identyfikator numeru identyfikacyjnego, który już istnieje, i zawiera fizyczne dostępne dane w lokalizacji magazynowej innej niż lokalizacja magazynu, w którym występuje rejestracja numeru identyfikacyjnego.

W scenariuszach zamówień przeniesienia, w których magazyn tranzytowy nie śledzi numerów identyfikacyjnych (a zatem nie śledzi fizycznych dostępnych zapasów powiązanych z numerem identyfikacyjnym), można użyć funkcji *Zapobiegaj wykorzystywaniu wysłanych numerów identyfikacyjnych z zamówień przeniesienia w magazynach innych niż magazyn docelowy* w celu uniemożliwienia fizycznej aktualizacji numerów identyfikacyjnych w tranzycie.

Aby udostępnić tę funkcję w systemie, należy włączyć *Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy* w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Aby zarządzać funkcjami, gdy ta funkcja jest dostępna, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Ogólne**, na skróconej karcie **Numery identyfikacyjne** w polu **Zasady dotyczące numerów identyfikacyjnych magazynu tranzytowego** określ jedną z następujących wartości:

    - **Zezwalaj na ponowne użycie nieśledzonego numeru identyfikacyjnego** — system działa tak samo, jak działa, gdy funkcja *Zapobiegaj używaniu numerów identyfikacyjnych wysłanych z zamówienia przeniesienia w magazynach innych niż magazyn docelowy* nie jest dostępna. Ta wartość jest ustawieniem domyślnym przy pierwszej aktywacji funkcji.
    - **Zapobiegaj ponownemu użyciu nieśledzonych numerów identyfikacyjnych** — w magazynie docelowym będą dozwolone tylko aktualizacje stanu zapasów związane ze wysyłką numeru identyfikacyjnego, dopóki zamówienie przeniesienia nie zostanie odebrane.

## <a name="more-information"></a>Więcej informacji

Aby uzyskać więcej informacji o elementach menu urządzeń przenośnych, zapoznaj się z tematem [Konfigurowanie urządzeń przenośnych do pracy magazynowej](configure-mobile-devices-warehouse.md).

Aby uzyskać więcej informacji oscenariuszu produkcji *Zgłoszenie wyrobów gotowych*, zapoznaj się z [Omówienie zasad pracy magazynowej](warehouse-work-policies.md).

Aby uzyskać więcej informacji o zarządzaniu ładunkami przychodzącymi, zajrzyj do [Obsługa magazynów dla ładunków przychodzących dla zamówień zakupu](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]