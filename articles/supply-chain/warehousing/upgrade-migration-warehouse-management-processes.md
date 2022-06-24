---
title: Uaktualnienie zarządzania magazynem z Microsoft Dynamics AX 2012 do Supply Chain Management
description: Ten artykuł zawiera omówienie opcji migracji dotyczących zarządzania produktami i magazynami.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d85f4e5c44db511970b3e22490341228fa0d1abd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857091"
---
# <a name="upgrade-warehouse-management-from-microsoft-dynamics-ax-2012-to-supply-chain-management"></a>Uaktualnienie zarządzania magazynem z Microsoft Dynamics AX 2012 do Supply Chain Management 


[!include [banner](../includes/banner.md)]

W tym artykule omówiono proces uaktualniania z Microsoft Dynamics AX 2012 R3, w którym działał moduł WMSII, do rozwiązania Supply Chain Management.

Program Supply Chain Management nie obsługuje już starszego modułu **WMSII** z Microsoft Dynamics AX 2012. Zamiast niego można używać modułu **Zarządzanie magazynem**. W module WMSII wymiary zapasów Lokalizacja i Identyfikator palety można było wybrać dla magazynu finansowego, jednak wymiar zapasów Identyfikator palety nie może być używany w magazynie finansowym w Supply Chain Management.

Podczas uaktualniania wszystkie produkty skojarzone z grupą wymiarów magazynowania używającą wymiaru zapasów Identyfikator palety są identyfikowane, oznaczane jako zablokowane i wyłączone z uaktualniania.

## <a name="upgrading-to-supply-chain-management-when-ax-2012-r3-wmsii-is-used"></a>Uaktualnianie do Supply Chain Management przy użyciu AX 2012 R3 WMSII
Po uaktualnieniu można użyć różnych opcji dostępnych w formularzu **Zmiana grupy wymiarów magazynowania dla towarów** i odblokować produkty, które zostały zablokowane podczas uaktualniania, a następnie wykonać transakcje na tych produktach.

### <a name="enabling-items-in-supply-chain-management"></a>Włączanie pozycji w Supply Chain Management 
Ta zmiana jest wymagana, ponieważ w rozwiązaniu Supply Chain Management elementem procesu zarządzania magazynem jest śledzenie towarów. W tych procesach wszystkie magazyny i ich lokalizacje muszą być skojarzone z profilem lokalizacji. Jeśli chcesz używać procesów zarządzania magazynem, należy dokonać następujących konfiguracji:
-   W istniejących magazynach musi zostać włączone używanie procesów zarządzania magazynem. 
-   Istniejące zwolnione produkty muszą zostać skojarzone z grupą wymiarów magazynowania, która używa procesów zarządzania magazynem. 

Jeśli źródłowe grupy wymiarów magazynowania używają wymiaru zapasów Identyfikator palety, lokalizacje istniejących dostępnych zapasów, które używały wymiaru zapasów Identyfikator palety, muszą być skojarzone z profilem lokalizacji, w którym zaznaczono parametr **Użyj opcji śledzenia numeru identyfikacyjnego**. Jeśli istniejący magazyn nie powinien być włączony do używania procesów zarządzania magazynem, można zmienić grupy wymiarów magazynowania istniejących dostępnych zapasów na grupy, które obsługują tylko wymiary zapasów Oddział, Magazyn i Lokalizacja. 

> [!NOTE] 
>  Grupę wymiarów magazynowania dla towarów można zmienić nawet wtedy, gdy istnieją otwarte transakcje magazynowe.

## <a name="find-products-that-were-blocked-because-of-pallet-id"></a>Znajdowanie produktów zablokowanych z powodu wymiaru zapasów Identyfikatora palety
Aby wyświetlić listę zwolnionych produktów, które zostały zablokowane podczas uaktualniania i nie mogą być przetwarzane, kliknij kolejno opcje **Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Zapasy** &gt; **Towary zablokowane dla aktualizacji zapasów**.

## <a name="change-storage-dimension-group-for-blocked-products"></a>Zmiana grupy wymiarów magazynowania dla zablokowanych produktów 
 
Aby towar mógł być używany w procesie zarządzania magazynem, musi być skojarzony z grupą wymiarów magazynowania, w której jest aktywny wymiar zapasów Lokalizacja i zaznaczony parametr **Użyj procesów zarządzania magazynami**. Gdy to ustawienie jest zaznaczone, wymiary zapasów Oddział, Magazyn, Stan zapasów, Lokalizacja i Numer identyfikacyjny stają się aktywne.

Aby odblokować produkty, które zostały zablokowane podczas uaktualniania, należy wybrać nową grupę wymiarów magazynowania dla tych produktów. Warto zauważyć, że grupę wymiarów magazynowania można zmienić nawet wtedy, gdy istnieją otwarte transakcje magazynowe. Aby używać towarów, które zostały zablokowane podczas uaktualniania, masz dwie opcje:

-   Zmiana grupy wymiarów magazynowania dla towaru na grupę wymiarów magazynowania, która używa tylko wymiarów zapasów Oddział, Magazyn i Lokalizacja. Wskutek tej zmiany wymiar zapasów Identyfikator palety przestaje być używany.
-   Zmiana grupy wymiarów magazynowania dla towaru na grupę wymiarów magazynowania, która używa procesów zarządzania magazynem. Wskutek tej zmiany zacznie być używany wymiar zapasów Numer identyfikacyjny.

## <a name="configure-warehouse-management-processes"></a>Konfigurowanie procesów zarządzania magazynami
Aby można było używać zwolnionych produktów w module **Zarządzanie magazynem**, produkty muszą używać grupy wymiarów magazynowania, w których zaznaczono parametr **Użyj procesów zarządzania magazynami**.

### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Włączanie używania procesów zarządzania magazynem w magazynach

1.  Utwórz co najmniej jeden nowy profil lokalizacji.
2.  Kliknij kolejno opcje **Zarządzanie magazynem** &gt; **Ustawienia** &gt; **Włącz procesy zarządzania magazynem** &gt; **Włącz konfigurowanie magazynu**.
3.  Na stronie **Włącz konfigurowanie magazynu** dodaj magazyn, który powinien być włączony. Ten krok można wykonać bezpośrednio na stronie lub za pomocą integracji z programem Microsoft Office.
4.  Przypisz profil lokalizacji do wszystkich lokalizacji. Ten krok można łatwo wykonać bezpośrednio ze strony, wykorzystując integrację z programem Microsoft Office. Można eksportować i importować dane lub używać funkcji przetwarzania jednostek danych dostępnych w module [Zarządzanie danymi](../../fin-ops-core/dev-itpro/data-entities/data-entities.md).
5.  Sprawdź poprawność zmian. W ramach procesu sprawdzania poprawności następują różne weryfikacje integralności danych. Jako część większego procesu uaktualniania może wystąpić konieczność rozwiązania zaistniałych problemów w implementacji źródłowej. W takim przypadku będzie potrzebne dodatkowe uaktualnienie danych.
6.  Wprowadź zmiany.

### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Zmiana grupy wymiarów magazynowania dla towarów, tak aby używała procesów zarządzania magazynem

1.  Utwórz nową wartość **Stan zapasów** i przypisz ją jako wartość **Domyślny identyfikator stanu zapasów** w oknie ustawień **Parametry zarządzania magazynem**.
2.  Utwórz nową grupę wymiarów magazynowania, w której zaznaczono parametr **Użyj procesów zarządzania magazynami**.
3.  Na stronie **Hierarchia rezerwacji** zdefiniuj nową hierarchię rezerwacji zgodnie z magazynem i grupami wymiarów śledzenia dla towaru.
4.  Utwórz jedną lub więcej grup numeracji jednostek, które zawierają co najmniej te same jednostki, jak używane do jednostek magazynowych towarów.
5.  Kliknij kolejno opcje **Zarządzanie magazynem** &gt; **Ustawienia** &gt; **Włącz procesy zarządzania magazynem** &gt; **Zmiana grupy wymiarów magazynowania dla towarów**.
6.  Na stronie **Zmiana grupy wymiarów magazynowania dla towarów** dodaj numery towarów, grup wymiarów magazynowania i grupy numeracji jednostek. Ten krok można wykonać bezpośrednio na stronie, wykorzystując integrację z programem Microsoft Office, lub przy użyciu przetwarzania jednostek danych w module [Zarządzanie danymi](../../fin-ops-core/dev-itpro/data-entities/data-entities.md).
7.  Sprawdź poprawność zmian. W ramach procesu sprawdzania poprawności następują różne weryfikacje integralności danych. Jako część większego procesu uaktualniania może wystąpić konieczność rozwiązania zaistniałych problemów w implementacji źródłowej. W takim przypadku będzie potrzebne dodatkowe uaktualnienie danych.
8.  Wprowadź zmiany. Aktualizacja wszystkich wymiarów zapasów może nieco potrwać. Można monitorować postęp za pomocą zadań wsadowych.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]