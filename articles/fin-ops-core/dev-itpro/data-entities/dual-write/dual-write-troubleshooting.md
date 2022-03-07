---
title: Rozwiązywanie ogólnych problemów
description: Ten temat zawiera ogólne informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami Finanse i Działania i Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f6f5b9f26990e2f4db9bf69040a6c4be31400b40
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062345"
---
# <a name="general-troubleshooting"></a>Rozwiązywanie ogólnych problemów

[!include [banner](../../includes/banner.md)]



Ten temat zawiera ogólne informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami Finanse i Działania i Dataverse.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Umożliwia włączenie i wyświetlenie logowania śledzenia wtyczki w Dataverse w celu wyświetlenia szczegółów błędu

**Wymagana rola do włączenia dziennika śledzenia i wyświetlenia błędów:** administrator systemu

Aby włączyć śledzenie, należy wykonać następujące kroki.

1. Zaloguj się do aplikacji angażującej klienta , otwórz stronę **Ustawień**, a następnie w obszarze **System** wybierz opcję **Administracja**.
2. Na stronie **Administracja** wybierz opcję **Konfiguracja systemu**.
3. Na karcie **Dostosowywanie**, w kolumnie **Wtyczki i niestandardowe śledzenie działania przepływu pracy** zaznacz opcję **Wszystkie**, aby włączyć dziennik śledzenia wtyczek. Jeśli chcesz rejestrować dzienniki śledzenia tylko w przypadku wystąpienia wyjątków, możesz zamiast tego wybrać **Wyjątek**.


Aby zobaczyć dziennik śledzenia, należy wykonać następujące kroki.

1. Zaloguj się do aplikacji angażującej klienta, otwórz stronę **Ustawień**, a następnie w obszarze **Dostosowywanie** wybierz opcję **Dziennik śledzenia wtyczek**.
2. Znajdź dzienniki śledzenia, w których w kolumnie **Nazwa typu** jest ustawiona wartość **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. Kliknij dwukrotnie towar, aby wyświetlić pełny dziennik, a następnie w skróconej karcie **Wykonania** przejrzyj tekst **Bloku wiadomości**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Włącz tryb debugowania w celu rozwiązywania problemów z synchronizacją na żywo w aplikacjach Finanse i Działania

**Wymagana rola w celu wyświetlania problemów:** administrator systemu

Błędy podwójnego zapisywania, które pochodzą z Dataverse, mogą pojawić się w aplikacji Finanse i Działania. Aby włączyć pełne rejestrowanie błędów, wykonując następujące kroki:

1. W przypadku wszystkich konfiguracji projektu w aplikacjach Finanse i Działania istnieje flaga **IsDebugMode** w tabeli **DualWriteProjectConfiguration**.
2. Otwórz tabelę **DualWriteProjectConfiguration** przy użyciu dodatku programu Excel. Aby użyć tego dodatku, włącz tryb projektowania w dodatku programu Excel Finanse i Działania i dodaj do arkusza konfigurację **DualWriteProjectConfiguration**. Więcej informacji można znaleźć w temacie [Wyświetlanie i aktualizowanie danych jednostki przy użyciu programu Excel](../../office-integration/use-excel-add-in.md).
3. Ustaw wartość **IsDebugMode** na **Tak** w projekcie.
4. Uruchom scenariusz, który generuje błędy.
5. Pełne dzienniki są przechowywane w tabeli **DualWriteErrorLog**.
6. W celu wyszukiwania danych w eksploratorze tabel użyj następującego łącza: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, zastępując wartość `999` stosownie do potrzeb.
7. Zaktualizuj ponownie po [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), który jest dostępny dla aktualizacji platformy 37 i nowszych. Jeśli ta poprawka jest zainstalowana, tryb debugowania zarejestruje więcej dzienników.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Sprawdź błędy synchronizacji na maszynie wirtualnej dla aplikacji Finanse i Działania

**Wymagana rola w celu wyświetlania problemów:** Administrator systemu

1. Zaloguj się do Microsoft Dynamics LifeCycle Services (LCS).
2. Otwórz projekt LCS, który wybrano do wykonania podwójnego zapisu.
3. Wybierz kafelek **Środowiska hostowane w chmurze**.
4. Użyj pulpitu zdalnego i zaloguj się do maszyny wirtualnej (VM) aplikacji Finanse i Działania. Należy skorzystać z konta lokalnego podanego w usługi LCS.
5. Otwórz Podgląd zdarzeń.
6. Wybierz do **Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacyjny**.
7. Przejrzyj listę ostatnio używanych błędów.

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Jak odłączyć i połączyć inne środowisko Dataverse z programu Finanse i Działania

**Wymagana rola do rozłączenia środowiska:** administrator systemu dla każdej aplikacji Finanse i Działania lub Dataverse.

1. Zaloguj się do aplikacji Finanse i Działania.
2. Przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz opcję **Podwójny zapis**.
3. Zaznacz wszystkie uruchomione mapowania i wybierz **Zatrzymaj**.
4. Wybierz **Odłącz środowisko**.
5. Wybierz **tak**, aby potwierdzić operację.

Teraz można połączyć nowe środowisko.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>Nie można wyświetlić formularza informacji o wierszu zamówienia sprzedaży 

Po utworzeniu zamówienia sprzedaży w systemie Dynamics 365 Sales, kliknięcie **+ Dodaj produkty** może spowodować przekierowanie do formularza wiersza zamówienia Dynamics 365 Project Operations. Nie ma sposobu na podstawie tego formularza, aby wyświetlić formularz **Informacji** o wierszu zamówienia sprzedaży. Opcja dotycząca **Informacji** nie jest wyświetlana w polu listy rozwijanej pod **Nowy wiersz zamówienia**. Dzieje się tak, ponieważ Project Operations zostało zainstalowane w danym środowisku.

Aby ponownie włączyć opcję formularza **Informacji**, wykonaj następujące kroki:

1. Przejdź do tabeli **Wiersz zamówienia**.
2. Znajdź formularz **Informacje** w węźle formularze.
3. Zaznacz formularz **Informacje** i kliknij pozycję **Włącz role zabezpieczeń**.
4. Zmień ustawienie zabezpieczeń, aby było **Wyświetlane dla wszystkich**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Włączanie i zapisywanie śledzenia sieciowego w celu dołączeniu śledzenia do biletów pomocy technicznej

Aby rozwiązać niektóre problemy, zespół pomocy technicznej może chcieć przejrzeć zapisy zdarzeń sieci. Aby utworzyć śledzenie sieci, należy wykonać następujące kroki:

### <a name="chrome"></a>Chrome

1. Na otwartej karcie naciśnij klawisz **F12** lub wybierz pozycję **Narzędzia deweloperskie**, aby otworzyć narzędzia deweloperskie.
2. Otwórz kartę **Sieć** i wpisz **integ** w polu tekstowym filtru.
3. Uruchom scenariusz i obserwuj rejestrowane żądania.
4. Kliknij prawym przyciskiem myszy wpisy i wybierz polecenie **Zapisz wszystko jako HAR z zawartością**.

### <a name="microsoft-edge"></a>Microsoft Edge

1. Na otwartej karcie naciśnij klawisz **F12** lub wybierz pozycję **Narzędzia deweloperskie**, aby otworzyć narzędzia deweloperskie.
2. Otwórz kartę **Sieć**.
3. Uruchom scenariusz.
4. Naciśnij przycisk **Zapisz**, aby wyeksportować wyniki do HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
