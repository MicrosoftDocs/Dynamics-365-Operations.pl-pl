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
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172721"
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

## <a name="self-reference-failures-during-initial-synchronization"></a>Błędy odwołują się do siebie podczas początkowej synchronizacji

Może się pojawić komunikat o błędzie podobnym do następującego przykładu, jeśli dowolne z mapowań ma odwołuje się do siebie:

*W przypadku Dostawców V2 następujący błąd: Identyfikator rekordu: nowy rekord, ErrorMessage: Nie można rozpoznać identyfikatora GUID dla pola: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Nie znaleziono wartości wyszukiwania: CN-001. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq „CN-001”*

Ten typ błędu występuje podczas wstępnej synchronizacji mapowań z odwołaniami do siebie. W poprzednim przykładzie pole konto faktury odwołuje się do jednostki dostawcy.

Aby rozwiązać ten problem, konieczne może być uruchomienie mapowania dwa razy przed zakończeniem synchronizacji początkowej.

