---
title: Konfigurowanie warunków wstępnych zarządzania brakiem zgodności
description: Ten temat umożliwia aktywowanie procesów zarządzania brakiem zgodności.
author: perlynne
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c4de822dcda604241416165a961e4b0bacaeb5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435480"
---
# <a name="set-up-prerequisites-for-nonconformance-management"></a>Konfigurowanie warunków wstępnych zarządzania brakiem zgodności

[!include [banner](../../includes/banner.md)]

Ten temat umożliwia aktywowanie procesów zarządzania brakiem zgodności. Brak zgodności opisuje procedurę lub towar, który ma problem z jakością, gdzie opisowe informacje zawierają źródło i typ problemu. Procedura wykorzystuje dane firmy demonstracyjnej USMF. Ta procedura jest zwykle wykonywana przez kierownika ds. jakości.


## <a name="enable-quality-management-processes-within-the-company"></a>Włączanie procesów zarządzania jakością w firmie
1. Otwórz w okienku nawigacji **Moduły > Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem**.
2. Kliknij kartę **Zarządzanie jakością**.
3. Wybierz opcję **tak** w polu **Użycie zarządzania jakością**, aby włączyć procesy zarządzania jakością dla firmy.
4. W polu **Stawka godzinowa** wpisz numer w walucie lokalnej. Stawka godzinowa używana jest do obliczania kosztów operacji związanych z niezgodnością. Stawka godzinowa i obliczone koszty stanowią odnośnikowe informacje o niezgodności i nie mają styczności z innymi funkcjami.  
5. Wybierz **Konfiguracja raportu**, aby określić typy uwag do raportów z kontroli jakości, które będą używane w różnych rodzajach raportów o zarządzaniu jakością.

## <a name="enable-user-for-nonconformance-processing"></a>Włączanie użytkownika dla przetwarzania braku zgodności
1. Otwórz w okienku nawigacji **Moduły > Administracja systemu > Użytkownicy > Użytkownicy**. 
2. Użyj szybkiego filtru, aby znaleźć użytkownika, który będzie zatwierdzał lub odrzucał rekordy braku zgodności. Na przykład wyfiltruj według pola **Nazwa** z wartością `Ricardo`. Aby wykonać zatwierdzenie braku zgodności, użytkownik, który zatwierdza lub odrzuca brak zgodności, musi mieć przypisaną wartość „Nazwa” na stronie **Użytkownicy**. Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.  
3. Umożliwia oznaczenie wiersza żądanego rekordu.
4. Wybierz **Opcje użytkownika**.
5. Kliknij kartę **Preferencje**.
6. W polu **Włącz obsługę dokumentów** zaznacz opcję **Tak**.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Definiowanie typów diagnostyki dla przetwarzania braku zgodności
1. W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Typy diagnostyki**. Na stronie **Typy diagnostyki** zdefiniuj klasyfikację akcji diagnostycznych. Korekta określa typ akcji diagnostycznej, którą należy wykonać dla zatwierdzonej niezgodności, osobę mającą wykonać tę akcję oraz żądaną i planowaną datę wykonania.  
2. Wybierz pozycję **Nowy**.
3. W polu **Diagnostyka** wpisz wartość.
4. W polu **Opis** wpisz wartość.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Definiowanie opłat związanych z kontrolą jakości dla przetwarzania braku zgodności
1. W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Opłaty związane z kontrolą jakości**. Strona **Opłaty związane z kontrolą jakości** służy do definiowania klasyfikacji opłat, które będą używane w operacjach związanych z brakiem zgodności.  
2. Wybierz pozycję **Nowy**.
3. W polu **Kod opłat** wpisz wartość.
4. W polu **Opis** wpisz wartość.

## <a name="define-the-operations-for-nonconformance-processing"></a>Definiowanie operacji przetwarzania braku zgodności
1. W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Działania operacyjne**. Za pomocą strony **Działania operacyjne** zdefiniuj klasyfikację pracy, którą można wykonać dla zatwierdzonego braku zgodności. Podczas kojarzenia operacji z brakiem zgodności można zdefiniować szczegółowe informacje o powiązanych materiałach, godzinach robocizny i opłatach dodatkowych wymaganych do wykonania operacji. Te informacje stanowią podstawę do obliczenia szacowanego kosztu wykonania operacji.  
2. Wybierz pozycję **Nowy**.
3. W polu **Działania operacyjne** wpisz wartość.
4. W polu **Opis** wpisz wartość.

## <a name="define-problem-types-for-nonconformance-processing"></a>Definiowanie typów problemów dla przetwarzania braku zgodności
1. W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Typy problemów**. Użyj strony **Typy problemów** do zdefiniowania klasyfikacji problemów z jakością, które występują w różnych typach braku zgodności. Istnieją następujące typy braku zgodności: **Wewnętrzny**, **Odbiorca**, **Dostawca**, **Żądanie usługi**, **Produkcja** i **Wytwarzanie produktu towarzyszącego**. Jeden typ problemu można skojarzyć z wieloma typami braku zgodności.  
2. Wybierz pozycję **Nowy**.
3. W polu **Typ problemu** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. Wybierz **Typy niezgodności**. Użyj strony **Typy niezgodności** w celu autoryzowania użycia typu problemu dla jednego lub więcej typów braku zgodności. Na przykład typ problemu związany z kodem wady może dotyczyć wszystkich typów niezgodności, podczas gdy typ problemu związany ze skargami odbiorców może dotyczyć tylko niezgodności typu odbiorca i zlecenie serwisowe.  
6. Wybierz pozycję **Nowy**.
7. W polu **Typ niezgodności** w nowym wierszu wybierz opcję.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Definiowanie stref kwarantanny dla przetwarzania braku zgodności
1. W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Ustawienia > Zarządzanie jakością > Strefy kwarantanny**.
2. Wybierz pozycję **Nowy**.
3. W polu **Strefa kwarantanny** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. Zamknij stronę.

