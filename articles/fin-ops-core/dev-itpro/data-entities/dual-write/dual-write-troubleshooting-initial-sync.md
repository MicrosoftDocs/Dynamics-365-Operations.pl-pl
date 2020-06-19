---
title: Rozwiązywanie problemów podczas synchronizacji początkowej
description: Ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410088"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Rozwiązywanie problemów podczas synchronizacji początkowej

[!include [banner](../../includes/banner.md)]

Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service. A dokładniej, ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Sprawdź, czy w aplikacji Finance and Operations nie występują błędy synchronizacji początkowej

Po włączeniu szablonów mapowania stan map powinien być **Uruchomione**. Jeśli stan jest **Nie uruchomione**, wystąpiły błędy podczas wstępnej synchronizacji. Aby wyświetlić błędy, wybierz kartę **Szczegóły wstępnej synchronizacji** na stronie **Podwójny zapis**.

![Karta Szczegóły wstępnej synchronizacji](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Nie można ukończyć synchronizacji początkowej: 400 złe żądanie

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Podczas próby uruchomienia mapowania i wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:

*Serwer zdalny zwrócił błąd: (400) złe żądanie.) Podczas eksportu AX napotkał błąd*

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

![Lista aplikacji Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Błędy odwołują się do siebie lub odwołują się cyklicznie podczas początkowej synchronizacji

Mogą pojawić się komunikaty o błędach, jeśli którekolwiek z mapowań zawierają odwołania do siebie lub odwołania cykliczne. Błędy należą do następujących kategorii:

- [Dostawcy (wersja 2) do mapowania jednostki msdyn_vendors](#error-vendor-map)
- [Mapowanie jednostki Dostawcy (wersja 3) do Kont](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a>Rozwiąż błąd w dostawcy V2 na mapowanie encji msdyn_vendors

Można uruchomić następujące błędy wstępne synchronizacji w przypadku mapowania **Dostawców V2** do **msdyn_vendors**, jeśli jednostki mają istniejące rekordy z wartościami w polach **PrimaryContactPersonId** i **InvoiceVendorAccountNumber**. Jest to spowodowane tym, że **InvoiceVendorAccountNumber** jest polem odwołującym się do siebie, a **PrimaryContactPersonId** jest odwołaniem cyklicznym w mapowaniu dostawcy.

*Nie można rozpoznać identyfikatora GUID dla pola: <field>. Nie znaleziono wyszukiwania: <value>. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne :https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

Oto kilka przykładów:

- *Nie można rozpoznać identyfikatora GUID dla pola: msdyn_vendorprimarycontactperson. msdyn_contactpersonid. Nie znaleziono wyszukiwania: 000056. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Nie można rozpoznać identyfikatora GUID dla pola: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. Nie znaleziono wyszukiwania: V24-1. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*

Jeśli istnieją rekordy z wartościami w tych polach jednostki dostawcy, należy wykonać kroki opisane w poniższej sekcji w celu pomyślnego zakończenia synchronizacji początkowej.

1. W aplikacji Finance and Operations usuń pola **PrimaryContactPersonId** i **InvoiceVendorAccountNumber** z mapowania i zapisz zmiany.

    1. Przejdź na stronę mapowanie podwójnego dostępu dla **Dostawcy V2 (msdyn_vendors)** i wybierz kartę **Mapowanie jednostek**. W lewym filtrze wybierz pozycję **Finance and Operations apps.Vendors V2**. W prawym filtrze wybierz opcję **Sales.Vendor**.

    2. Wyszukaj **primarycontactperson**, aby odnaleźć pole źródłowe **PrimaryContactPersonId**.
    
    3. Kliknij przycisk **Akcje** i wybierz opcję **Usuń**.
    
        ![odwołanie własne lub cykliczne 3](media/vend_selfref3.png)
    
    4. Powtórz tę czynność, aby usunąć pole **InvoiceVendorAccountNumber**.
    
        ![odwołanie własne lub cykliczne 4](media/vend-selfref4.png)
    
    5. Zapisz zmiany mapowania.

2. Wyłącz śledzenie zmian dla jednostki **Dostawcy V2**.

    1. Przejdź do **Zarządzanie danymi \> Jednostki danych**.
    
    2. Wybierz jednostkę **Dostawcy V2**.
    
    3. Kliknij opcję **Opcje** na pasku menu, a następnie **Zmień śledzenie**.
    
        ![odwołanie własne lub cykliczne 5](media/selfref_options.png)
    
    4. Kliknij **Wyłącz śledzenie zmian**.
    
        ![odwołanie własne lub cykliczne 6](media/selfref_tracking.png)

3. Uruchom synchronizację wstępną mapowania **Dostawców V2 (msdyn_vendors)**. Synchronizacja początkowa powinna zostać pomyślnie uruchomiona bez żadnych błędów.

4. Uruchom synchronizację początkową dla mapowania **Kontaktów z CDS V2 (kontakty)**. Należy zsynchronizować to mapowanie, jeśli ma zostać zsynchronizowane główne pole kontaktu w jednostce dostawcy, ponieważ rekordy kontaktów muszą być zsynchronizowane jako wstępne.

5. Dodaj pola **PrimaryContactPersonId** i **InvoiceVendorAccountNumber** z powrotem do mapowania **Dostawcy v2 (msdyn_vendors)** i zapisz mapowanie.

6. Uruchom ponowanie synchronizację wstępną mapowania **Dostawców V2 (msdyn_vendors)**. Wszystkie rekordy zostaną zsynchronizowane, ponieważ śledzenie zmian jest wyłączone.

7. Włącz śledzenie zmian dla jednostki **Dostawcy V2**.

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a>Rozwiąż błąd w mapowaniu jednostki Klienci V3 do Kont

Można uruchomić następujące błędy wstępne synchronizacji w przypadku mapowania **Klienci V3** do **Kont**, jeśli jednostki mają istniejące rekordy z wartościami w polach **ContactPersonID** i **InvoiceAccount**. Jest to spowodowane tym, że **InvoiceAccount** jest polem odwołującym się do siebie, a **ContactPersonID** jest odwołaniem cyklicznym w mapowaniu dostawcy.

*Nie można rozpoznać identyfikatora GUID dla pola: <field>. Nie znaleziono wyszukiwania: <value>. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne :https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

- *Nie można rozpoznać identyfikatora GUID dla pola: primarycontactid.msdyn_contactpersonid. Nie znaleziono wyszukiwania: 000056. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Nie można rozpoznać identyfikatora GUID dla pola: msdyn_billingaccount.accountnumber. Nie znaleziono wyszukiwania: 1206-1. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*

Jeśli istnieją rekordy z wartościami w tych polach jednostki klienta, należy wykonać kroki opisane w poniższej sekcji w celu pomyślnego zakończenia synchronizacji początkowej. Z tego podejścia można skorzystać w przypadku dowolnych z pudełkych jednostek, takich jak konta i kontakty.

1. W aplikacji Finance and Operations usuń pola **ContactPersonID** i **InvoiceAccount** z mapowania **Klienci V3 (konta)** i zapisz mapowanie.

    1. Przejdź na stronę mapowanie podwójnego dostępu dla **Klienci V3 (konta)** i wybierz kartę **Mapowanie jednostek** . W lewym filtrze wybierz pozycję **Finance and Operations app.Customers V3**. W prawym filtrze wybierz **Common Data Service.Account**.

    2. Wyszukaj **contactperson**, aby odnaleźć pole źródłowe **ContactPersonID**.
    
    3. Kliknij przycisk **Akcje** i wybierz opcję **Usuń**.
    
        ![odwołanie własne lub cykliczne 3](media/cust_selfref3.png)
    
    4. Powtórz tę czynność, aby usunąć pole **InvoiceAccount**.
    
        ![odwołanie własne lub cykliczne](media/cust_selfref4.png)
    
    5. Zapisz zmiany mapowania.

2. Wyłącz śledzenie zmian dla jednostki **Klienci V3**.

    1. Przejdź do **Zarządzanie danymi \> Jednostki danych**.
    
    2. Wybierz jednostkę **Klienci V3**.
    
    3. Kliknij opcję **Opcje** na pasku menu, a następnie **Zmień śledzenie**.
    
        ![odwołanie własne lub cykliczne 5](media/selfref_options.png)
    
    4. Kliknij **Wyłącz śledzenie zmian**.
    
        ![odwołanie własne lub cykliczne 6](media/selfref_tracking.png)

3. Uruchom synchronizację początkową dla mapowania **Klienci V3 (Konta)**. Synchronizacja początkowa powinna zostać pomyślnie uruchomiona bez żadnych błędów.

4. Uruchom synchronizację początkową dla mapowania **Kontaktów z CDS V2 (kontakty)**. Istnieją 2 mapy o tej samej nazwie. Wybierz ten z opisem **Szablon podwójnego zapisu do synchronizacji między kontaktami dostawcy FO.CDS V2 do CDS.Contacts. Wymaga nowego pakietu \[Dynamics365SupplyChainExtended\].** na karcie **Szczegóły** mapu.

5. Dodaj pola **InvoiceAccount** i **ContactPersonId** z powrotem do mapowania **Klienci V3 (Konta)** i zapisz mapowanie. Teraz zarówno pole **InvoiceAccount**, jak i pole **ContactPersonId** są ponownie częścią trybu synchronizacji na żywo. W następnym kroku przeprowadź synchronizację początkową tych pól.

6. Uruchom znowu synchronizację początkową dla mapowania **Klienci V3 (Konta)**. Ponieważ śledzenie zmian jest wyłączone, uruchomienie synchronizacji spowoduje zsynchronizowanie danych dla **InvoiceAccount** i **ContactPersonId** z aplikacji Finance and Operations do Common Data Service.

7. Aby synchronizować dane dla **InvoiceAccount** i **ContactPersonId** z Common Data Service do Finance and Operations, należy skorzystać z projektu integracji danych.

    1. W Power Apps utwórz projekt integracji danych między jednostkami **Sales.Account** i **Finance and Operations apps.Customers V3**. Kierunek danych musi być z Common Data Service do aplikacji Finance and Operations.  Ponieważ **InvoiceAccount** jest nowym atrybutem w podwójnym zapisywaniu, celowe może być pominięcie synchronizacji początkowej dla tego atrybutu. Aby uzyskać więcej informacji, zobacz [Integrowanie danych z Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).

        Na poniższym obrazie przedstawiono projekt, który aktualizuje **CustomerAccount** i **ContactPersonId**.

        ![odwołanie własne lub cykliczne](media/cust_selfref6.png)

    2. Dodaj kryteria firmy w polu filtruj po stronie Common Data Service, ponieważ w aplikacji Finance and Operations zostanie zaktualizowana tylko liczba rekordów spełniających kryteria filtru. Aby dodać filtr, kliknij ikonę filtr. W oknie dialogowym **Edytuj** kwerendę można dodać kwerendę filtru, taką jak **_msdyn_company_value eq '\<guid\>'**. Jeśli ikona filtru nie istnieje, utwórz bilet pomocy technicznej, aby poprosić zespół integracji danych o umożliwienie obsługi filtru w dzierżawie. Jeśli kwerenda filtru nie zostanie wprowadzona dla **_msdyn_company_value**, wszystkie rekordy zostaną zsynchronizowane.

        ![odwołanie własne lub cykliczne](media/cust_selfref7.png)

        Spowoduje to ukończenie początkowej synchronizacji rekordów.

8. Wyłącz śledzenie zmian dla jednostki **Klienci V3** w aplikacji Finance and Operations.

