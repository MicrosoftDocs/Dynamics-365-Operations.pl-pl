---
title: Rozwiązywanie problemów podczas synchronizacji początkowej
description: Ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.
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
ms.openlocfilehash: 9a6be5f4e08a92171892549c017c15c66b1bde2e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350819"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Rozwiązywanie problemów podczas synchronizacji początkowej

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse. A dokładniej, ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Sprawdź, czy w aplikacji Finance and Operations nie występują błędy synchronizacji początkowej

Po włączeniu szablonów mapowania stan map powinien być **Uruchomione**. Jeśli stan jest **Nie uruchomione**, wystąpiły błędy podczas wstępnej synchronizacji. Aby wyświetlić błędy, wybierz kartę **Szczegóły wstępnej synchronizacji** na stronie **Podwójny zapis**.

![Błąd na karcie Szczegóły początkowej synchronizacji.](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Nie można ukończyć synchronizacji początkowej: 400 złe żądanie

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Podczas próby uruchomienia mapowania i wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:

*(\[Złe żądanie\], Serwer zdalny zwrócił błąd: (400) złe żądanie.) Podczas eksportu AX napotkał błąd*

Oto przykład tabeli pełnego komunikatu o błędzie.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

Jeśli ten błąd występuje zawsze i nie można ukończyć wstępnej synchronizacji, należy wykonać poniższe kroki w celu rozwiązania problemu.

1. Zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations.
2. Otwórz Microsoft Management Console.
3. Upewnij się, że w okienku **Usługi** jest uruchomiona usługa struktury eksportu danych Microsoft Dynamics 365. Uruchom ją ponownie, jeśli została zatrzymana, ponieważ wymaga tego synchronizacja wstępna.

## <a name="initial-synchronization-error-403-forbidden"></a>Błąd synchronizacji początkowej: 403 zabroniony

Podczas wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:

*(\[Zabroniony\], serwer zdalny zwrócił błąd: (403) Zabroniony.) Podczas eksportu AX napotkał błąd*

Aby naprawić problem, należy wykonać następujące czynności.

1. Zaloguj się do aplikacji Finance and Operations.
2. Na stronie **aplikacje Azure Active Directory** usuń klienta **DtAppID**, a następnie dodaj go ponownie.

![Klient DtAppID na liście aplikacji Azure AD.](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Błędy odwołują się do siebie lub odwołują się cyklicznie podczas początkowej synchronizacji

Mogą pojawić się komunikaty o błędach, jeśli którekolwiek z mapowań zawierają odwołania do siebie lub odwołania cykliczne. Błędy należą do następujących kategorii:

- [Błędy w mapowaniu tabeli dostawców V2-na-msdyn_vendors](#error-vendor-map)
- [Błędy w mapowaniu tabeli Klienci V3 do Kont](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>Rozwiązywanie błędów w mapowaniu tabeli dostawców V2-na-msdyn_vendors

Można napotkać następujące błędy wstępne synchronizacji w przypadku mapowania **Dostawców V2** do **msdyn\_vendors**, jeśli tabeli mają istniejące wiersze z wartościami w kolumnach **PrimaryContactPersonId** i **InvoiceVendorAccountNumber**. Błędy są spowodowane tym, że **InvoiceVendorAccountNumber** jest kolumną odwołującą się do siebie, a **PrimaryContactPersonId** jest odwołaniem cyklicznym w mapowaniu dostawcy.

Otrzymane komunikaty o błędach będą miały następujący format:

*Nie można rozpoznać identyfikatora GUID dla pola: \<field\>. Nie znaleziono wyszukiwania: \<value\>. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Oto kilka przykładów:

- *Nie można rozpoznać identyfikatora GUID dla pola: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. Nie znaleziono wyszukiwania: 000056. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Nie można rozpoznać identyfikatora GUID dla pola: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Nie znaleziono wyszukiwania:  V24-1. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

Jeśli istnieją wiersze w tabeli dostawcy mają wartości w kolumnach **PrimaryContactPersonId** i **InvoiceVendorAccountNumber**, należy wykonać kroki opisane w poniższej sekcji w celu pomyślnego zakończenia synchronizacji początkowej.

1. W aplikacji Finance and Operations usuń kolumny **PrimaryContactPersonId** i **InvoiceVendorAccountNumber** z mapowania i zapisz mapowanie.

    1. Przejdź na stronę mapowanie podwójnego dostępu dla **Dostawcy V2 (msdyn\_vendors)** i wybierz kartę **Mapowanie tabeli**. W lewym filtrze wybierz pozycję **Finance and Operations apps.Vendors V2**. W prawym filtrze wybierz opcję **Sales.Vendor**.
    2. Wyszukaj **primarycontactperson**, aby odnaleźć kolumnę źródłową **PrimaryContactPersonId**.
    3. Wybierz opcję **Akcje**, a następnie wybierz opcję **Usuń**.

        ![Usuwanie kolumny PrimaryContactPersonId.](media/vend_selfref3.png)

    4. Powtórz te kroki, aby usunąć kolumnę **InvoiceVendorAccountNumber**.

        ![Usuwanie kolumny InvoiceVendorAccountNumber.](media/vend-selfref4.png)

    5. Zapisz zmiany w mapowaniu.

2. Wyłącz śledzenie zmian dla tabeli **Dostawcy V2**.

    1. W obszarze roboczym **Zarządzanie danymi** wybierz kafelek **Tabele danych**.
    2. Wybierz tabelę **Dostawcy V2**.
    3. W okienku akcji wybierz opcję **Opcje**, a następnie wybierz opcję **Śledzenie zmian**.

        ![Wybieranie opcji śledzenia zmian.](media/selfref_options.png)

    4. Wybierz **Wyłącz śledzenie zmian**.

        ![Wybór opcji Wyłącz śledzenie zmian.](media/selfref_tracking.png)

3. Uruchom synchronizację wstępną mapowania **Dostawców V2 (msdyn\_vendors)**. Synchronizacja początkowa powinna zostać pomyślnie uruchomiona bez żadnych błędów.
4. Uruchom synchronizację początkową dla mapowania **Kontaktów z CDS V2 (kontakty)**. Musisz zsynchronizować to odwzorowanie, jeśli chcesz zsynchronizować podstawową kolumnę kontaktu w tabeli dostawcy, ponieważ początkowa synchronizacja musi być również wykonana dla wierszy kontaktów.
5. Dodaj kolumny **PrimaryContactPersonId** i **InvoiceVendorAccountNumber** z powrotem do mapowania **Dostawcy v2 (msdyn\_vendors)** i zapisz mapowanie.
6. Uruchom ponownie synchronizację wstępną mapowania **Dostawców V2 (msdyn\_vendors)**. Ponieważ śledzenie zmian jest wyłączone, wszystkie wiersze zostaną zsynchronizowane.
7. Wyłącz ponownie śledzenie zmian dla tabeli **Dostawcy V2**.

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>Rozwiąż błędy w mapowaniu tabeli Klienci V3-do-Kont

Można napotkać następujące błędy wstępne synchronizacji w przypadku mapowania **Klienci V3** do **Kont**, jeśli tabele mają istniejące wiersze z wartościami w kolumnach **ContactPersonID** i **InvoiceAccount**. Te błędy są spowodowane tym, że **InvoiceAccount** jest kolumną odwołującą się do siebie, a **ContactPersonID** jest odwołaniem cyklicznym w mapowaniu dostawcy.

Otrzymane komunikaty o błędach będą miały następujący format:

*Nie można rozpoznać identyfikatora GUID dla pola: \<field\>. Nie znaleziono wyszukiwania: \<value\>. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Oto kilka przykładów:

- *Nie można rozpoznać identyfikatora GUID dla pola: primarycontactid.msdyn\_contactpersonid. Nie znaleziono wyszukiwania: 000056. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Nie można rozpoznać identyfikatora GUID dla pola: msdyn\_billingaccount.accountnumber. Nie znaleziono wyszukiwania: 1206-1. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

Jeśli istnieją wiersze w tabeli klienta mają wartości w kolumnach **ContactPersonID** i **InvoiceAccount**, należy wykonać kroki opisane w poniższej sekcji w celu pomyślnego zakończenia synchronizacji początkowej. Z tego podejścia można skorzystać w przypadku dowolnych gotowych tabel, takich jak **Konta** i **Kontakty**.

1. W aplikacji Finance and Operations usuń kolumny **ContactPersonID** i **InvoiceAccount** z mapowania **Klienci V3 (konta)** i nstępnie zapisz mapowanie.

    1. Na stronie mapowanie podwójnego dostępu dla **Klienci V3 (konta)** i wybierz kartę **Mapowanie tabeli** . W lewym filtrze wybierz pozycję **Finance and Operations app.Customers V3**. W prawym filtrze wybierz **Dataverse.Account**.
    2. Wyszukaj **contactperson**, aby odnaleźć kolumnę źródłową **ContactPersonID**.
    3. Wybierz opcję **Akcje**, a następnie wybierz opcję **Usuń**.

        ![Usuwanie kolumny ContactPersonID.](media/cust_selfref3.png)

    4. Powtórz te kroki, aby usunąć kolumnę **InvoiceAccount**.

        ![Usuwanie kolumny InvoiceAccount.](media/cust_selfref4.png)

    5. Zapisz zmiany w mapowaniu.

2. Wyłącz śledzenie zmian dla tabeli **Klienci V3**.

    1. W obszarze roboczym **Zarządzanie danymi** wybierz kafelek **Tabele danych**.
    2. Wybierz tabelę **Klient (wersja 3)**.
    3. W okienku akcji wybierz opcję **Opcje**, a następnie wybierz opcję **Śledzenie zmian**.

        ![Wybieranie opcji śledzenia zmian.](media/selfref_options.png)

    4. Wybierz **Wyłącz śledzenie zmian**.

        ![Wybór opcji Wyłącz śledzenie zmian.](media/selfref_tracking.png)

3. Uruchom synchronizację początkową dla mapowania **Klienci V3 (Konta)**. Synchronizacja początkowa powinna zostać pomyślnie uruchomiona bez żadnych błędów.
4. Uruchom synchronizację początkową dla mapowania **Kontaktów z CDS V2 (kontakty)**.

    > [!NOTE]
    > Istnieją dwa mapy o tej samej nazwie. Pamiętaj, aby wybrać mapę, która ma następujący opis na karcie **Szczegóły**: **Szablon 2Dual-write do synchronizacji między kontaktami dostawcy FO.CDS V2 i CDS. Wymaga nowego pakietu \[Dynamics365SupplyChainExtended\].**

5. Dodaj kolumny **InvoiceAccount** i **ContactPersonId** z powrotem do mapowania **Klienci V3 (Konta)** i nastepnie zapisz mapowanie. Teraz zarówno kolumna **InvoiceAccount**, jak i kolumna **ContactPersonId** są ponownie częścią trybu synchronizacji na żywo. W następnym kroku wykonasz synchronizację początkową dla tych kolumn.
6. Uruchom ponownie synchronizację początkową dla mapowania **Klienci V3 (Konta)**. Ponieważ śledzenie zmian jest wyłączone, dae dla **InvoiceAccount** i **ContactPersonId** będą zsynchronizowane z aplikacji Finance and Operations do Dataverse.
7. Aby synchronizować dane dla **InvoiceAccount** i **ContactPersonId** z Dataverse do aplikacji Finance and Operations, należy skorzystać z projektu integracji danych.

    1. W Power Apps utwórz projekt integracji danych między tabelami **Sales.Account** i **Finance and Operations apps.Customers V3**. Kierunek danych musi być z Dataverse do aplikacji Finance and Operations. Ponieważ **InvoiceAccount** jest nowym atrybutem w podwójnym zapisywaniu, można pominąć synchronizację początkową dla niego. Aby uzyskać więcej informacji, zobacz [Integrowanie danych z Dataverse](/power-platform/admin/data-integrator).

        Na poniższej ilustracji przedstawiono projekt, który aktualizuje **CustomerAccount** i **ContactPersonId**.

        ![Projekt integracji danych w celu zaktualizowania CustomerAccount i ContactPersonId.](media/cust_selfref6.png)

    2. Dodaj kryteria firmy w polu filtruj po stronie Dataverse, aby w aplikacji Finance and Operations została zaktualizowana tylko liczba wierszy spełniających kryteria filtru. Aby dodać filtr, kliknij przycisk filtru. W oknie dialogowym **Edytuj kwerendę** można dodać kwerendę filtru, taką jak **\_msdyn\_company\_value eq '\<guid\>'**. 

        > [UWAGA] Jeśli przycisk filtru nie istnieje, utwórz bilet pomocy technicznej, aby poprosić zespół integracji danych o umożliwienie obsługi filtru w dzierżawie.

        Jeśli kwerenda filtru nie zostanie wprowadzona dla **\_msdyn\_company\_value**, wszystkie wiersze zostaną zsynchronizowane.

        ![Dodawanie kwerendy filtru.](media/cust_selfref7.png)

    Początkowa synchronizacja wierszy jest teraz zakończona.

8. W aplikacji Finance and Operations wyłącz śledzenie zmian dla tabeli **Klienci (wersja 3)**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]