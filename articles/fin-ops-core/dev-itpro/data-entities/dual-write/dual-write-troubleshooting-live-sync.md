---
title: Rozwiązywanie problemów z synchronizacją na żywo
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a0a14c87af7f0d2372d752233f21d9accbca58a8
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542522"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Rozwiązywanie problemów z synchronizacją na żywo

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse. Ten temat zawiera informacje, które mogą pomóc w rozwiązaniu problemów związanych z synchronizacją na żywo.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a>Synchronizacja na żywo powoduje, że podczas tworzenia wiersza w aplikacji Finance and Operations jest zgłaszany błąd 403 Zabroniony

Może pojawić się następujący komunikat o błędzie podczas tworzenia wiersza w aplikacji Finance and Operations:

*\[{\\„błąd\\”:{\\„kod\\”:\\„0x 80072560\\”,\\„komunikat\\”:\\„użytkownik nie jest członkiem organizacji.\\”}}\], Serwer zdalny zwrócił błąd: (403) zabroniony”}}”.*

Aby rozwiązać ten problem, należy wykonać kroki opisane w [Wymagania systemowe i wymagania wstępne](requirements-and-prerequisites.md). Aby wykonać te kroki, użytkownicy aplikacji podwójnego odpisu, którzy utworzyli w Dataverse, muszą mieć rolę administratora systemu. Domyślny zespół będący właścicielem musi mieć również rolę Administratora systemu.

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a>Synchronizacja na żywo dla jakiejkolwiek tabeli powoduje, że podczas tworzenia wiersza w aplikacji Finance and Operations jest wciąż zgłaszany podobny błąd

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Przy każdej próbie zapisania danych tabeli w aplikacji Finance and Operations może pojawić się komunikat o błędzie podobny do następującego:

*Nie można zapisać zmian w bazie danych. Jednostka pracy nie może zatwierdzić transakcji. Nie można zapisać danych do jednostki uoms. Zapis do UnitOfMeasureEntity nie powiódł się. Komunikatu o błędzie nie można zsynchronizować z jednostką uoms.*

Aby rozwiązać ten problem, należy upewnić się, że istnieją dane referencyjne wymagań wstępnych w aplikacji Finance and Operations i Dataverse. Jeśli na przykład odbiorca należący do danej aplikacji Finance and Operations należy do konkretnej grupy odbiorców, należy upewnić się, że Grupa odbiorców istnieje w Dataverse.

Jeśli istnieją dane po obu stronach i potwierdzono, że ten błąd nie jest związany z danymi, wykonaj następujące kroki.

1. Zatrzymaj powiązaną tabelę.
2. Zaloguj się do aplikacji Finance and Operations i upewnij się, że w tabelach DualWriteProjectConfiguration i DualWriteProjectFieldConfiguration istnieją wiersze dla tabeli, której dotyczy niepowodzenie. Oto przykład zapytania, które wygląda tak jak w przypadku niepowodzenia tabeli **Klienci**.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. Jeśli istnieją wiersze dla tabeli, której dotyczy błąd, nawet po zatrzymaniu mapowania tabeli, usuń te wiersze, które są powiązane z niepowodzeniem dla tabeli. Należy zwrócić uwagę na kolumnę **projectname** w tabeli DualWriteProjectConfiguration i pobrać wiersz w tabeli DualWriteProjectFieldConfiguration, używając nazwy projektu w celu usunięcia wiersza.
4. Rozpocznij mapowanie tabeli. Sprawdź, czy dane są zsynchronizowane bez problemów.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Obsługa błędów uprawnień do odczytu lub odczytu podczas tworzenia danych w aplikacji Finance and Operations

Podczas tworzenia danych w aplikacji Finance and Operations może pojawić się komunikat o błędzie „Złe żądanie”, który przypomina poniższy przykład.

![Przykład komunikatu o błędzie złego żądania.](media/error_record_id_source.png)

Aby rozwiązać ten problem, należy przypisać poprawną rolę zabezpieczeń zespołowi zamapowanej jednostki biznesowej usługi Dynamics 365 Customer Service lub Dynamics 365 Sales w celu włączenia brakującego uprawnienia.

1. W aplikacji Finance and Operations znajdź jednostkę biznesową, która jest zamapowana w zestawie połączenia integracji danych.

    ![Mapowanie organizacji.](media/mapped_business_unit.png)

2. Zaloguj się do środowiska w aplikacji angażującej klienta, przejdź do **Ustawienia \> Zabezpieczenia** i znajdź zespół zamapowanej jednostki biznesowej.

    ![Zespół zamapowanej jednostki biznesowej.](media/setting_security_page.png)

3. Otwórz stronę zespołu do edycji, a następnie wybierz pozycję **Zarządzaj rolami**, aby otworzyć okno dialogowe **Zarządzanie rolami zespołu**.

    ![Przycisk Zarządzaj rolami.](media/manage_team_roles.png)

4. Przypisz rolę, która ma uprawnienie odczyt/zapis dla odpowiednich tabel, a następnie kliknij przycisk **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Poprawianie problemów z synchronizacją w środowisku, w którym jest ostatnio zmienione środowisko Dataverse

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Może pojawić się następujący komunikat o błędzie podczas tworzenia danych w aplikacji Finance and Operations:

*{„EntityName”: „CustCustomerV3Entity”, „executionStatus”: 2, „fieldResponses”:\[\], „recordResponses”:\[{„ErrorMessage”: „**nie można wygenerować ładunku dla jednostki CustCustomerV3Entity**”, „logDateTime”: „2019-08-27T 18:51:52.5843124Z”, „verboseError”: „Tworzenie ładunku nie powiodło się z powodu błędu nieprawidłowy identyfikator URI: identyfikator URI jest pusty”}\], „isErrorCountUpdated”: prawda}*

Oto jak wygląda błąd w aplikacji angażującej klienta:

*Wystąpił nieoczekiwany błąd w kodzie ISV. (Błąd = ClientError) Nieoczekiwany wyjątek od wtyczki (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: nie można przetworzyć konta jednostki — (Próba połączenia nie powiodła się, ponieważ połączona strona nie odpowiedziała prawidłowo po upływie określonego czasu lub ustanowienie połączenia nie powiodło się, ponieważ połączony host nie odpowiedział*

Ten błąd występuje, gdy środowisko Dataverse jest niepoprawnie resetowane w trakcie próby utworzenia danych w aplikacji Finance and Operations.

Aby naprawić problem, należy wykonać następujące czynności.

1. Zaloguj się do maszyny wirtualnej (VM) Finance and Operations, otwórz program SQL Server Management Studio (SSMSE) i wyszukaj wiersze w tabeli DUALWRITEPROJECTCONFIGURATIONENTITY, gdzie **internalentityname** oznacza **Odbiorców v3** i **externalentityname** równą **konta**. Oto, co ma wyglądać kwerenda.

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

3. Upewnij się, że kolumna **externalenvironmentURL** ma poprawny Dataverse lub adres URL aplikacji. Usuń wszystkie zduplikowane wiersze, które wskazują na nieprawidłowy adres URL Dataverse. Usuń odpowiednie wiersze z tabel DUALWRITEPROJECTFIELDCONFIGURATION i DUALWRITEPROJECTCONFIGURATION.
4. Zatrzymaj mapowanie tabeli, a następnie uruchom je ponownie

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
