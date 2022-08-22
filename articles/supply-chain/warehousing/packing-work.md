---
title: Praca pakowania do pakowania kontenerów wychodzących i przetwarzania wysyłek
description: W tym artykule opisano typ zlecenia „Pakowanie”, który zarządza pracą nad kontenerami dostawczymi i obsługuje częściowe wysyłki zapakowanych kontenerów powiązane z ładunkami, w których pozostają niezapakowane towary magazynowe.
author: perlynne
ms.date: 7/13/2022
ms.topic: article
ms.search.form: WHSPackingWorkLocationSetup, WHSPack, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 34a7087df7e7768d0012ea4f534aa109654af8fa
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220592"
---
# <a name="packing-work-for-packing-outbound-containers-and-processing-shipments"></a>Praca pakowania do pakowania kontenerów wychodzących i przetwarzania wysyłek

[!include [banner](../../includes/banner.md)]

W tym artykule opisano typ zlecenia *Pakowanie*, który zarządza pracą nad kontenerami dostawczymi i obsługuje częściowe wysyłki zapakowanych kontenerów powiązane z ładunkami, w których pozostają niezapakowane towary magazynowe. Praca pakowania umożliwia używanie funkcji [potwierdzania i przenoszenia](confirm-and-transfer.md) w celu potwierdzania wysyłek wychodzących skojarzonych z kontenerami.

Praca pakowania jest tworzona automatycznie, gdy zapasy związane z pracą z dokumentem źródłowym są odkładane w lokalizacjach typu *Lokalizacja* pakowania. Praca składa się z dwóch wierszy, po jednej dla *pobrania* i drugiej dla *Odłożenie*, i jest automatycznie zachowywana jako część procesu zamknięcia/ponownego otwarcia kontenera.

Aby uzyskać więcej informacji dotyczących sposobu skonfigurowania i używania procesu pakowania kontenerów, zobacz temat [Kontenery załadunkowe do wysyłki](packing-containers.md).

## <a name="turn-on-the-feature"></a>Włączanie funkcji

Jeśli Twój system nie zawiera jeszcze funkcji opisanych w tym artykule, przejdź do [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje w następującej kolejności. Obie funkcje dotyczą modułu **Zarządzania magazynem**.

1. *Potwierdź i przenieś*
1. *Praca pakowania dla stacji pakowania*

## <a name="set-up-a-location-for-packing-work"></a>Skonfiguruj miejsce do pakowania

Użyj poniższej procedury, aby ustawić miejsca pakowania. Dla każdej lokalizacji można określić, czy system automatycznie tworzy pracę w pakowaniu.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Konfiguracja stacji pakowania**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać rekord konfiguracji stacji pakowania.
1. W nowym rekordzie ustaw następujące pola:

    - **Magazyn** — Wybierz lub wprowadź magazyn, w którym znajduje się lokalizacja pakowania.
    - **Lokalizacja** – wprowadź lub wybierz wartość. Ta lokalizacja musi być przypisana do profilu lokalizacji, w którym jest używany typ lokalizacji skonfigurowany jako typ lokalizacji pakowania dla firmy, **na stronie Parametry zarządzania magazynem**. Aby uzyskać więcej informacji, zobacz temat [Kontenery paczek do wysyłki](packing-containers.md).
    - **Utwórz pracę pakowania** — zaznaczenie tego pola wyboru umożliwia tworzenie pracy pakowania za każdym razem, gdy towary są dostarczane do lokalizacji pakowania. Praca będzie zawierać łącza do powiązanych wierszy ładunku, dzięki czemu można zapakować i wysłać ładunki częściowe.

## <a name="example-scenario"></a>Przykładowy scenariusz

W tym przykładzie przedstawiono sposób przetwarzania przepływu wychodzącego zamówienia sprzedaży przez pakowanie kontenera i wysyłanie częściowego ładunku.

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/fin-ops/get-started/demo-data.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

Tych scenariuszy można również używać jako wskazówek dotyczących korzystania z danej funkcji podczas pracy w produkcji. Jednak w takim przypadku należy podstawić własne wartości dla każdego ustawienia opisanego w tym polu.

### <a name="configure-packing-work-for-warehouse-packing-location"></a>Konfigurowanie pracy pakowania dla lokalizacji pakowania do magazynu

Aby rozpocząć, należy skonfigurować proces *pracy pakowania* dla określonego magazynu i lokalizacji.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Opakowanie \> Konfiguracja stacji pakowania**.
1. W okienku akcji wybierz **Nowe**, aby dodać rekord konfiguracji.
1. W nowym rekordzie ustaw następujące wartości:

    - **Magazyn:** *62*
    - **Lokalizacja:** *Pakiet*
    - **Utwórz pracę pakowania:** *Tak*

1. Zamknij stronę **Konfiguracja stacji pakowania** od płatności.

### <a name="create-a-load-template-that-allows-partial-shipping"></a>Utwórz szablon ładunku, który umożliwia częściową wysyłkę

Aby umożliwić dostawę ładunku w wielu wysyłkach, należy go skojarzyć z szablonem ładunku umożliwiającym częściową wysyłkę. Wykonaj poniższe czynności, aby utworzyć wymagany szablon.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Ładunek \> Szablony ładunku**.
1. W okienku akcji wybierz **Nowe**, aby dodać rekord konfiguracji.
1. W nowym rekordzie ustaw następujące wartości:

    - **Identyfikator szablonu ładunku:** *Częściowy*
    - **Zezwalaj na podział ładunku w trakcie potwierdzania wysyłki:** *Tak*

1. Zamknij stronę **Załaduj szablony**.

Aby uzyskać więcej informacji, Sprawdź temat [Potwierdź i przenieś](Confirm-and-transfer.md).

### <a name="process-a-sales-order"></a>Przetwórz zamówienie sprzedaży

Aby przetwarzać zamówienie sprzedaży i częściowo je wysyłać, należy wykonać następujące kroki.

1. Wypełnij przykładowy [scenariusz](packing-containers.md#scenario) podany w kontenerach zapakowych [do wysyłki](packing-containers.md). W tym scenariuszu tworzy się zamówienie sprzedaży dla dwóch sztuk jednego towaru. Następnie należy zapakować tylko jedną z sztuk do kontenera i zamknąć kontener. Należy zanotować identyfikator wysyłki, który należy utworzyć, zgodnie z instrukcjami w scenariuszu.
1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca\> Wszystkie prace**.
1. W obszarze filtru zaznacz pole wyboru **Pokaż zamkniętą pracę**. Następnie wprowadź identyfikator wysyłki w polu **Filtruj** i wybierz filtrowanie według wartości **identyfikatora wysyłki**. Powinny być teraz dostępne trzy nagłówki pracy. Jedna z nich jest dla pracy pobierania zamówienia sprzedaży i ma stan *Zamknięte*. Dwa z nich są związane z procesem pakowania: jedna z nich jest powiązana z zamkniętym kontenerem i ma stan *Zamknięty*, a druga – z rozpakowaniem pozostałego towaru i ma stan *Otwarte*.
1. Wybierz wartość **identyfikatora ładunku** dla dowolnego nagłówka pracy, aby otworzyć stronę **szczegółów ładunku** dla ładunku.
1. Przełącz do widoku **nagłówka**.
1. Na skróconej **karcie Ogólne** wybierz przycisk **Edytuj** dla pola **Identyfikator szablonu ładunku**. Następnie wybierz szablon częściowego ładunku wysyłki utworzony dla tego scenariusza (*Częściowe*).
1. W okienku akcji na karcie **Wyślij i odbierz** w grupie **Potwierdź** kliknij opcję **Przesyłka wychodząca**.
1. W oknie dialogowym **Potwierdzenie wysyłki** wybierz opcję **Podziel ilość do nowego ładunku**.
1. Kliknij przycisk **OK**.

Wysłano jeden kontener powiązany z oryginalnym ładunkiem, a system utworzył nowy ładunek dla pozostałych towarów, które wciąż muszą zostać zapakowane w kontenery.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
