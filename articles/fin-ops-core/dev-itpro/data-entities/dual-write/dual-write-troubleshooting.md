---
title: Rozwiązywanie ogólnych problemów
description: Ten temat zawiera informacje dotyczące ogólnego rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.
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
ms.openlocfilehash: f7ee0b5aa4e72614205e129acd986376b33efc70
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172698"
---
# <a name="general-troubleshooting"></a>Rozwiązywanie ogólnych problemów

[!include [banner](../../includes/banner.md)]



Ten temat zawiera informacje dotyczące ogólnego rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a>Podczas próby zainstalowania pakietu podwójnego odpisu za pomocą narzędzia package deployer nie są wyświetlane żadne dostępne rozwiązania

Niektóre wersje narzędzia package deployer są niezgodne z pakietem rozwiązania podwójnego zapisywania. Aby pomyślnie zainstalować pakiet, należy pamiętać o użyciu [wersji 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) lub nowszej narzędzia package deployer.

Po zainstalowaniu narzędzia package deployer zainstaluj pakiet rozwiązania, wykonując poniższe kroki.

1. Pobierz najnowszy plik pakietu rozwiązania z Yammer.com. Po pobraniu pliku zip Package kliknij go prawym przyciskiem myszy i wybierz polecenie **Właściwości**. Zaznacz pole wyboru **Odblokuj**, a następnie kliknij przycisk **Zastosuj**. Jeśli pole wyboru **Odblokuj** nie jest widoczne, plik zip jest już odblokowany i można pominąć ten krok.

    ![Okno dialogowe Właściwości](media/unblock_option.png)

2. Wyodrębnij plik zip pakietu i skopiuj wszystkie pliki w folderze **Dynamics365FinanceAndOperationsCommon. PackageDeployer.2.0.438**.

    ![Zawartość folderu Dynamics365FinanceAndOperationsCommon. PackageDeployer.2.0.438](media/extract_package.png)

3. Wklej wszystkie skopiowane pliki do folderu **Narzędzia** narzędzia package deployer. 
4. Uruchom **PackageDeployerexe**, aby wybrać środowisko Common Data Service i zainstalować rozwiązania.

    ![Zawartość folderu Narzędzia](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a>Umożliwia włączenie i wyświetlenie logowania śledzenia wtyczki w Common Data Service w celu wyświetlenia szczegółów błędu

**Wymagana rola do włączenia dziennika śledzenia i wyświetlenia błędów:** administrator systemu

Aby włączyć śledzenie, należy wykonać następujące kroki.

1. Zaloguj się do aplikacji Finance and Operations, otwórz stronę **Ustawień**, a następnie w obszarze **System** wybierz opcję **Administracja**.
2. Na stronie **Administracja** wybierz opcję **Konfiguracja systemu**.
3. Na karcie **Dostosowywanie**, w polu **Wtyczki i niestandardowe śledzenie działania przepływu pracy** zaznacz opcję **Wszystkie**, aby włączyć dziennik śledzenia wtyczek. Jeśli chcesz rejestrować dzienniki śledzenia tylko w przypadku wystąpienia wyjątków, możesz zamiast tego wybrać **Wyjątek**.


Aby zobaczyć dziennik śledzenia, należy wykonać następujące kroki.

1. Zaloguj się do aplikacji Finance and Operations, otwórz stronę **Ustawień**, a następnie w obszarze **Dostosowywanie** wybierz opcję **Dziennik śledzenia wtyczek**.
2. Znajdź dzienniki śledzenia, w których w polu **Nazwa typu** jest ustawiona wartość **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.
3. Kliknij dwukrotnie towar, aby wyświetlić pełny dziennik, a następnie w skróconej karcie **Wykonania** przejrzyj tekst **Bloku wiadomości**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Włącz tryb debugowania w celu rozwiązywania problemów z synchronizacją na żywo w aplikacjach Finance and Operations

**Wymagana rola w celu wyświetlania problemów:** administrator systemu

Błędy podwójnego zapisywania, które pochodzą z Common Data Service, mogą pojawić się w aplikacji Finance and Operations. W niektórych przypadkach pełny tekst komunikatu o błędzie jest niedostępny, ponieważ wiadomość jest zbyt długa lub zawiera informacje identyfikacyjne (dane osobowe). Pełne rejestrowanie błędów można włączyć, wykonując następujące kroki:

1. Wszystkie konfiguracje projektu w aplikacjach Finance and Operations mają właściwość **IsDebugMode** w jednostce **DualWriteProjectConfiguration**. Otwórz jednostkę **DualWriteProjectConfiguration** przy użyciu dodatku programu Excel.

    > [!TIP]
    > Łatwym sposobem otwarcia jednostki jest włączenie trybu **Projektowania** w dodatku Excel, a następnie dodanie **DualWriteProjectConfigurationEntity** do arkusza. Aby uzyskać więcej informacji, zobacz: [Otwieranie danych jednostki w programie Excel i aktualizowanie ich przy użyciu dodatku programu Excel](../../office-integration/use-excel-add-in.md).

2. Właściwość **IsDebugMode** należy skonfigurować jako wartość **Tak** dla projektu.
3. Uruchom scenariusz, który generuje błędy.
4. Pełne dzienniki są dostępne w tabeli DualWriteErrorLog. Aby wyszukać dane w przeglądarce, należy wybrać następujący adres URL (w razie potrzeby zastąpić **XXX**):

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Sprawdź błędy synchronizacji na maszynie wirtualnej dla aplikacji Finance and Operations

**Wymagana rola w celu wyświetlania problemów:** administrator systemu

1. Zaloguj się do Microsoft Dynamics LifeCycle Services (LCS).
2. Otwórz projekt LCS, który wybrano do wykonania podwójnego zapisu.
3. Wybierz kafelek **Środowiska hostowane w chmurze**.
4. Użyj pulpitu zdalnego i zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations. Należy skorzystać z konta lokalnego podanego w usługi LCS.
5. Otwórz Podgląd zdarzeń.
6. Wybierz do **Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacyjny**.
7. Przejrzyj listę ostatnio używanych błędów.

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a>Odłącz i Połącz inne środowisko Common Data Service z poziomu aplikacji Finance and Operations

**Wymagane poświadczenia do odłączenia środowiska:** administrator dzierżawy Azure AD

1. Zaloguj się do aplikacji Finance and Operations.
2. Przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz opcję **Podwójny zapis**.
3. Zaznacz wszystkie uruchomione mapowania i wybierz **Zatrzymaj**.
4. Wybierz **Odłącz środowisko**.
5. Wybierz **tak**, aby potwierdzić operację.

Teraz można połączyć nowe środowisko.
