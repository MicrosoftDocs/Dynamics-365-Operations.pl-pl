---
title: Rozwiązywanie problemów z synchronizacją na żywo
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 82bdcc71196c22689cc65601f98187aaa9e5e9d6
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997309"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Rozwiązywanie problemów z synchronizacją na żywo

[!include [banner](../../includes/banner.md)]



Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service. Ten temat zawiera informacje, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>Synchronizacja na żywo powoduje, że podczas tworzenia rekordu w aplikacji Finance and Operations jest zgłaszany błąd 403 Zabroniony

Może pojawić się następujący komunikat o błędzie podczas tworzenia zapisu w aplikacji Finance and Operations:

*\[{\\„błąd\\”:{\\„kod\\”:\\„0x 80072560\\”,\\„komunikat\\”:\\„użytkownik nie jest członkiem organizacji.\\”}}\], Serwer zdalny zwrócił błąd: (403) zabroniony”}}”.*

Aby rozwiązać ten problem, należy wykonać kroki opisane w [Wymagania systemowe i wymagania wstępne](requirements-and-prerequisites.md). Aby wykonać te kroki, użytkownicy aplikacji podwójnego odpisu, którzy utworzyli w Common Data Service, muszą mieć rolę administratora systemu. Domyślny zespół będący właścicielem musi mieć również rolę Administratora systemu.

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>Synchronizacja na żywo dla jakiejkolwiek firmy powoduje, że podczas tworzenia zapisu w aplikacji Finance and Operations jest wciąż zgłaszany podobny błąd

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Przy każdej próbie zapisania danych jednostki w aplikacji Finance and Operations może pojawić się komunikat o błędzie podobny do następującego:

*Nie można zapisać zmian w bazie danych. Jednostka pracy nie może zatwierdzić transakcji. Nie można zapisać danych do jednostki uoms. Zapis do UnitOfMeasureEntity nie powiódł się. Komunikatu o błędzie nie można zsynchronizować z jednostką uoms.*

Aby rozwiązać ten problem, należy upewnić się, że istnieją dane referencyjne wymagań wstępnych w aplikacji Finance and Operations i Common Data Service. Jeśli na przykład odbiorca należący do danej aplikacji Finance and Operations należy do konkretnej grupy odbiorców, należy upewnić się, że Grupa odbiorców istnieje w Common Data Service.

Jeśli istnieją dane po obu stronach i potwierdzono, że ten błąd nie jest związany z danymi, wykonaj następujące kroki.

1. Zatrzymaj powiązaną jednostkę.
2. Zaloguj się do aplikacji Finance and Operations i upewnij się, że w tabelach DualWriteProjectConfiguration i DualWriteProjectFieldConfiguration istnieją rekordy dla jednostki, której dotyczy niepowodzenie. Oto przykład kwerendy, która wygląda tak jak w przypadku niepowodzenia jednostki **Klienci**.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. Jeśli istnieją rekordy dla jednostki, której dotyczy błąd, nawet po zatrzymaniu mapowania jednostki, usuń te rekordy, które są powiązane z niepowodzeniem. Należy zwrócić uwagę na kolumnę **projectname** w tabeli DualWriteProjectConfiguration i pobrać rekord w tabeli DualWriteProjectFieldConfiguration, używając nazwy projektu w celu usunięcia zapisu.
4. Rozpocznij mapowanie jednostki. Sprawdź, czy dane są zsynchronizowane bez problemów.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Obsługa błędów uprawnień do odczytu lub odczytu podczas tworzenia danych w aplikacji Finance and Operations

Podczas tworzenia danych w aplikacji Finance and Operations może pojawić się komunikat o błędzie „Złe żądanie”, który przypomina poniższy przykład.

![Przykład komunikatu o błędzie złego żądania](media/error_record_id_source.png)

Aby rozwiązać ten problem, należy przypisać poprawną rolę zabezpieczeń zespołowi zamapowanej jednostki biznesowej usługi Dynamics 365 Customer Service lub Dynamics 365 Sales w celu włączenia brakującego uprawnienia.

1. W aplikacji Finance and Operations znajdź jednostkę biznesową, która jest zamapowana w zestawie połączenia integracji danych.

    ![Mapowanie organizacji](media/mapped_business_unit.png)

2. Zaloguj się do środowiska w aplikacji na podstawie modelu w Dynamics 365, przejdź do **Ustawienia \> Zabezpieczenia** i znajdź zespół zamapowanej jednostki biznesowej.

    ![Zespół zamapowanej jednostki biznesowej](media/setting_security_page.png)

3. Otwórz stronę zespołu do edycji, a następnie wybierz pozycję **Zarządzaj rolami** , aby otworzyć okno dialogowe **Zarządzanie rolami zespołu**.

    ![Przycisk Zarządzaj rolami](media/manage_team_roles.png)

4. Przypisz rolę, która ma uprawnienie odczyt/zapis dla odpowiednich jednostek, a następnie kliknij przycisk **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a>Poprawianie problemów z synchronizacją w środowisku, w którym jest ostatnio zmienione środowisko Common Data Service

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Może pojawić się następujący komunikat o błędzie podczas tworzenia danych w aplikacji Finance and Operations:

*{„EntityName”: „CustCustomerV3Entity”, „executionStatus”: 2, „fieldResponses”:\[\], „recordResponses”:\[{„ErrorMessage”: „ **nie można wygenerować ładunku dla jednostki CustCustomerV3Entity** ”, „logDateTime”: „2019-08-27T 18:51:52.5843124Z”, „verboseError”: „Tworzenie ładunku nie powiodło się z powodu błędu nieprawidłowy identyfikator URI: identyfikator URI jest pusty”}\], „isErrorCountUpdated”: prawda}*

Oto, jak wygląda błąd w aplikacji opartej na modelu w Dynamics 365:

*Wystąpił nieoczekiwany błąd w kodzie ISV. (Błąd = ClientError) Nieoczekiwany wyjątek od wtyczki (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: nie można przetworzyć konta jednostki — (Próba połączenia nie powiodła się, ponieważ połączona strona nie odpowiedziała prawidłowo po upływie określonego czasu lub ustanowienie połączenia nie powiodło się, ponieważ połączony host nie odpowiedział*

Ten błąd występuje, gdy środowisko Common Data Service jest niepoprawnie resetowane w trakcie próby utworzenia danych w aplikacji Finance and Operations.

Aby naprawić problem, należy wykonać następujące czynności.

1. Zaloguj się do maszyny wirtualnej (VM) Finance and Operations, otwórz program SQL Server Management Studio (SSMSE) i wyszukaj rekordy w tabeli DUALWRITEPROJECTCONFIGURATIONENTITY, gdzie **internalentityname** oznacza **Odbiorców v3** i **externalentityname** równą **konta**. Oto, co ma wyglądać kwerenda.

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. Za pomocą nazwy projektu z wyników poprzedniej kwerendy uruchom następującą kwerendę.

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. Upewnij się, że kolumna **externalenvironmentURL** ma poprawny Common Data Service lub adres URL aplikacji. Usuń wszystkie zduplikowane rekordy, które wskazują na nieprawidłowy adres URL Common Data Service. Usuń odpowiednie rekordy z tabel DUALWRITEPROJECTFIELDCONFIGURATION i DUALWRITEPROJECTCONFIGURATION.
4. Zatrzymaj mapowanie jednostki, a następnie uruchom je ponownie
