---
title: "Migracja produktów i zarządzanie magazynem z systemu AX 2012 do rozwiązania Finance and Operations"
description: "Ten temat zawiera omówienie opcji migracji dotyczących zarządzania produktami i magazynami."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7c6d40e3b80a0974c722ad3a88a29adc8dedf585
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="migrate-products-and-warehouse-management-from-ax-2012-to-finance-and-operations"></a>Migracja produktów i zarządzanie magazynem z systemu AX 2012 do rozwiązania Finance and Operations

W tym temacie omówiono opcje migracji funkcji zarządzania produktami i magazynami dostępne w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

<a name="introduction"></a>Wprowadzenie
------------

Podczas uaktualniania do programu Finance and Operations produkty są blokowane, jeśli są skojarzone z grupą wymiarów magazynowania mającą ustawienia niezgodne z wymaganiami ustawień grupy wymiarów magazynowania w programie Finance and Operations. Jednak po uaktualnieniu można użyć różnych opcji migracji dostępnych w procesie **Zmiana grupy wymiarów magazynowania dla towarów** i odblokować produkty, które zostały zablokowane podczas uaktualniania. Następnie można przetwarzać transakcje dla tych produktów. Niektóre towary mogą już być skojarzone z grupami wymiarów magazynowania, w których wymiary Oddział, Magazyn i Zapasy w lokalizacji są aktywne i fizycznie śledzone. W takim przypadku można użyć procesu **Zmiana grupy wymiarów magazynowania dla towarów**, aby włączyć dla tych towarów możliwość używania w procesach zarządzania magazynem. Ta funkcja jest użyteczna, jeśli chcesz korzystać z funkcji zarządzania magazynem dla istniejących towarów.

## <a name="upgrading-to-finance-and-operations-when-ax-2012-r3-wmsii-is-used"></a>Uaktualnianie do programu Finance and Operations, gdy jest używane oprogramowanie AX 2012 R3 WMSII
Program Finance and Operations nie obsługuje już starszego modułu **WMSII** z systemu Microsoft Dynamics AX 2012. Zamiast niego można używać nowego modułu **Zarządzanie magazynem**. W poprzednich wersjach wymiary zapasów Lokalizacja i Identyfikator palety może było wybierać dla zapasów finansowych. Jednak w ramach procesu uaktualniania usunięto możliwość włączania wymiaru zapasów Identyfikator palety dla zapasów finansowych. Wszystkie produkty skojarzone z grupą wymiarów magazynowania, która używa wymiaru zapasów Identyfikator palety, zostaną zablokowane i nie będą przetwarzane.

### <a name="enabling-items-in-finance-and-operations"></a>Włączanie towarów w rozwiązaniu Finance and Operations

W programie Finance and Operations towary, które będą używane w procesach zarządzania magazynem, muszą być skojarzone z grupą wymiarów magazynowania, która ma zaznaczony parametr **Użyj procesów zarządzania magazynami**. Gdy to ustawienie jest zaznaczone, wymiary zapasów Oddział, Magazyn, Stan zapasów, Lokalizacja i Numer identyfikacyjny stają się aktywne. Można zmienić na ten typ grupy wymiarów magazynowania tylko dla towarów już skojarzonych z grupami wymiarów magazynowania, w których wymiar zapasów Lokalizacja jest aktywny.

### <a name="items-that-are-blocked-for-inventory-updates"></a>Towary zablokowane dla aktualizacji zapasów

Aby wyświetlić listę zwolnionych produktów, które zostały zablokowane podczas uaktualniania i nie mogą być przetwarzane, kliknij kolejno opcje **Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Zapasy** &gt; **Towary zablokowane dla aktualizacji zapasów**.

### <a name="reapplying-blocked-products"></a>Ponowne stosowanie zablokowanych produktów

Aby odblokować produkty, które zostały zablokowane podczas uaktualniania, należy wybrać nową grupę wymiarów magazynowania dla tych produktów. Warto zauważyć, że grupę wymiarów magazynowania można zmienić nawet wtedy, gdy istnieją otwarte transakcje magazynowe. Aby używać towarów, które zostały zablokowane podczas uaktualniania, masz dwie opcje:

-   Zmiana grupy wymiarów magazynowania dla towaru na grupę wymiarów magazynowania, która używa tylko wymiarów zapasów Oddział, Magazyn i Lokalizacja. Wskutek tej zmiany wymiar zapasów Identyfikator palety przestaje być używany.
-   Zmiana grupy wymiarów magazynowania dla towaru na grupę wymiarów magazynowania, która używa procesów zarządzania magazynem. Wskutek tej zmiany zacznie być używany wymiar zapasów Numer identyfikacyjny.

### <a name="migration-processes"></a>Procesy migracji

W rozwiązaniu Finance and Operations elementem procesu zarządzania magazynem jest śledzenie towarów. W tych procesach wszystkie magazyny i ich lokalizacje muszą być skojarzone z profilem lokalizacji. Pod względem koncepcyjnym jeśli mają być używane procesy zarządzania magazynem, muszą być obsługiwane dwa procesy:

-   W istniejących magazynach musi być włączone używanie procesów zarządzania magazynem.
-   Istniejące zwolnione produkty muszą być skojarzone z nową grupą wymiarów magazynowania, która używa procesów zarządzania magazynem.

Jeśli źródłowe grupy wymiarów magazynowania używają wymiaru zapasów Identyfikator palety, lokalizacje istniejących dostępnych zapasów, które używały wymiaru zapasów Identyfikator palety, muszą być skojarzone z profilem lokalizacji, w którym zaznaczono parametr **Użyj opcji śledzenia numeru identyfikacyjnego**. Jeśli istniejący magazyn nie powinien być włączony do używania procesów zarządzania magazynem, można zmienić grupy wymiarów magazynowania istniejących dostępnych zapasów na grupy, które obsługują tylko wymiary zapasów Oddział, Magazyn i Lokalizacja.

### <a name="using-the-warehouse-management-processes"></a>Używanie procesów zarządzania magazynem

Aby można było używać zwolnionych produktów w module **Zarządzanie magazynem**, produkty muszą używać grupy wymiarów magazynowania, w których zaznaczono parametr **Użyj procesów zarządzania magazynami**.

#### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Włączanie używania procesów zarządzania magazynem w magazynach

1.  Utwórz co najmniej jeden nowy profil lokalizacji.
2.  Kliknij kolejno opcje **Zarządzanie magazynem** &gt; **Ustawienia** &gt; **Włącz procesy zarządzania magazynem** &gt; **Włącz konfigurowanie magazynu**.
3.  Na stronie **Włącz konfigurowanie magazynu** dodaj magazyn, który powinien być włączony. Ten krok można wykonać bezpośrednio na stronie lub za pomocą integracji z programem Microsoft Office.
4.  Przypisz profil lokalizacji do wszystkich lokalizacji. Ten krok można łatwo wykonać bezpośrednio ze strony, wykorzystując integrację z programem Microsoft Office. Można eksportować i importować dane lub używać funkcji przetwarzania jednostek danych dostępnych w module [Zarządzanie danymi](../../dev-itpro/data-entities/data-entities.md).
5.  Sprawdź poprawność zmian. W ramach procesu sprawdzania poprawności następują różne weryfikacje integralności danych. Jako część większego procesu uaktualniania może wystąpić konieczność rozwiązania zaistniałych problemów w implementacji źródłowej. W takim przypadku będzie potrzebne dodatkowe uaktualnienie danych.
6.  Wprowadź zmiany.

#### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Zmiana grupy wymiarów magazynowania dla towarów, tak aby używała procesów zarządzania magazynem

1.  Utwórz nową wartość **Stan zapasów** i przypisz ją jako wartość **Domyślny identyfikator stanu zapasów** w oknie ustawień **Parametry zarządzania magazynem**.
2.  Utwórz nową grupę wymiarów magazynowania, w której zaznaczono parametr **Użyj procesów zarządzania magazynami**.
3.  Na stronie **Hierarchia rezerwacji** zdefiniuj nową hierarchię rezerwacji zgodnie z magazynem i grupami wymiarów śledzenia dla towaru.
4.  Utwórz jedną lub więcej grup numeracji jednostek, które zawierają co najmniej te same jednostki, jak używane do jednostek magazynowych towarów.
5.  Kliknij kolejno opcje **Zarządzanie magazynem** &gt; **Ustawienia** &gt; **Włącz procesy zarządzania magazynem** &gt; **Zmiana grupy wymiarów magazynowania dla towarów**.
6.  Na stronie **Zmiana grupy wymiarów magazynowania dla towarów** dodaj numery towarów, grup wymiarów magazynowania i grupy numeracji jednostek. Ten krok można wykonać bezpośrednio na stronie, wykorzystując integrację z programem Microsoft Office, lub przy użyciu przetwarzania jednostek danych w module [Zarządzanie danymi](../../dev-itpro/data-entities/data-entities.md).
7.  Sprawdź poprawność zmian. W ramach procesu sprawdzania poprawności następują różne weryfikacje integralności danych. Jako część większego procesu uaktualniania może wystąpić konieczność rozwiązania zaistniałych problemów w implementacji źródłowej. W takim przypadku będzie potrzebne dodatkowe uaktualnienie danych.
8.  Wprowadź zmiany. Aktualizacja wszystkich wymiarów zapasów może nieco potrwać. Można monitorować postęp za pomocą zadań wsadowych.



