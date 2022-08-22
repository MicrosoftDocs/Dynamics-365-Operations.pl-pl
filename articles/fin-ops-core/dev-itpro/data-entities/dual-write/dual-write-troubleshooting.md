---
title: Rozwiązywanie ogólnych problemów
description: Ten artykuł zawiera ogólne informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: be3d72063ac18b9abea77d5aec6e230b0c930ae6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289369"
---
# <a name="general-troubleshooting"></a>Rozwiązywanie ogólnych problemów

[!include [banner](../../includes/banner.md)]



Ten artykuł zawiera ogólne informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse.

> [!IMPORTANT]
> Niektóre problemy z tego artykułu mogą wymagać roli administratora systemu lub poświadczeń administratora klienta usługi Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Umożliwia włączenie i wyświetlenie logowania śledzenia wtyczki w Dataverse w celu wyświetlenia szczegółów błędu

Dzienniki śledzenia mogą być przydatne przy rozwiązywaniu problemów związanych z synchronizacją na żywo między funkcjami Finanse & Operations i Dataverse. Dzienniki mogą dostarczać konkretnych szczegółów zespołom, które zapewniają pomoc techniczną i inżynieryjną w systemie Dynamics 365. W tym artykule opisano sposób włączania dzienników śledzenia i sposobu ich wyświetlania. Dzienniki śledzenia są zarządzane na stronie Ustawienia usługi Dynamics 365 i wymagają uprawnień na poziomie administratora, aby je zmieniać i wyświetlać. 

**Wymagana rola do włączenia dziennika śledzenia i wyświetlenia błędów:** administrator systemu

### <a name="turn-on-the-trace-log"></a>Włączanie dziennika śledzenia
Aby włączyć śledzenie, należy wykonać następujące kroki.

1.  Zaloguj się do systemu Dynamics 365, a następnie wybierz **Ustawienia** w górnym pasku nawigacji. Na stronie Systemy kliknij przycisk **Administracja**.
2.  Na stronie Administracja wybierz opcję **Konfiguracja systemu**.
3.  Wybierz kartę **Dostosowywanie** i wtyczkę, a następnie w sekcji Śledzenie aktywności niestandardowego przepływu pracy zmień opcję rozwijaną na **Wszystko**. Pozwala to śledzić wszystkie działania i dostarczać pełny zestaw danych zespołom, które muszą przeglądać potencjalne problemy.

> [!NOTE]
> Ustawienie opcji na liście rozwijanej **Wyjątek** zapewnia informacje śledzenia tylko w przypadku wystąpienia wyjątków (błędów).

Po włączeniu dzienniki śledzenia dodatku będą zbierane aż do ich ręcznego wyłączenia przez powrót do tej lokalizacji i wybranie **opcji Wyłączone**.

### <a name="view-the-trace-log"></a>Wyświetlanie dziennika śledzenia
Aby zobaczyć dziennik śledzenia, należy wykonać następujące kroki.

1. Na stronie Ustawienia systemu Dynamics 365, a następnie wybierz **Ustawienia** w górnym pasku nawigacji. 
2. Wybierz **pozycję Dziennik śledzenia** dodatku plug-in w sekcji **Dostosowania** strony.
3. Wpisy znajdują się na liście dzienników śledzenia na podstawie typu Nazwa lub Nazwa komunikatu.
4. Otwórz żądany wpis, aby wyświetlić pełny dziennik. Sekcja Blokada komunikatów w sekcji Wykonanie będzie zawierała dostępne informacje dotyczące dodatku. Jeśli jest dostępna, zostaną również podane szczegóły wyjątków. 

Można skopiować zawartość dzienników śledzenia i wkleić je do innej aplikacji, np. notatnika lub innego narzędzia, aby przejrzeć dzienniki lub pliki tekstowe, aby łatwiej wyświetlić całą zawartość. 

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Włącz tryb debugowania w celu rozwiązywania problemów z synchronizacją na żywo w aplikacjach finansowych i operacyjnych

**Wymagana rola w celu wyświetlania problemów:** administrator systemu

Błędy podwójnego zapisywania, które pochodzą z Dataverse, mogą pojawić się w aplikacjach finansowych i operacyjnych. Aby włączyć pełne rejestrowanie błędów, wykonując następujące kroki:

1. W przypadku wszystkich konfiguracji projektu w aplikacjach finansowych i operacyjnych istnieje flaga **IsDebugMode** w tabeli **DualWriteProjectConfiguration**.
2. Otwórz tabelę **DualWriteProjectConfiguration** przy użyciu dodatku programu Excel. Aby użyć tego dodatku, włącz tryb projektowania w dodatku w aplikacjach finansowych i operacyjnych dla Excela i dodaj do arkusza konfigurację **DualWriteProjectConfiguration**. Więcej informacji można znaleźć w temacie [Wyświetlanie i aktualizowanie danych jednostki przy użyciu programu Excel](../../office-integration/use-excel-add-in.md).
3. Ustaw wartość **IsDebugMode** na **Tak** w projekcie.
4. Uruchom scenariusz, który generuje błędy.
5. Pełne dzienniki są przechowywane w tabeli **DualWriteErrorLog**.
6. W celu wyszukiwania danych w eksploratorze tabel użyj następującego łącza: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, zastępując wartość `999` stosownie do potrzeb.
7. Zaktualizuj ponownie po [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), który jest dostępny dla aktualizacji platformy 37 i nowszych. Jeśli ta poprawka jest zainstalowana, tryb debugowania zarejestruje więcej dzienników.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Sprawdź błędy synchronizacji na maszynie wirtualnej dla aplikacji finansowych i operacyjnych

**Wymagana rola w celu wyświetlania problemów:** Administrator systemu

1. Zaloguj się do Microsoft Dynamics LifeCycle Services (LCS).
2. Otwórz projekt LCS, który wybrano do wykonania podwójnego zapisu.
3. Wybierz kafelek **Środowiska hostowane w chmurze**.
4. Użyj pulpitu zdalnego i zaloguj się do maszyny wirtualnej (VM) aplikacji finansowych i operacyjnych. Należy skorzystać z konta lokalnego podanego w usługi LCS.
5. Otwórz Podgląd zdarzeń.
6. Wybierz do **Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacyjny**.
7. Przejrzyj listę ostatnio używanych błędów.

## <a name="dual-write-ui-landing-page-showing-blank"></a>Strona docelowa interfejsu użytkownika dwóch zapisów pokazująca puste pole
Podczas otwierania strony z podwójnym zapisem w przeglądarce Microsoft Edge lub Google Chrome strona główna nie ładuje się i wyświetlana jest pusta strona lub błąd, taki jak „Coś poszło nie tak”.
W narzędziach Devtools występuje błąd w dziennikach konsoli:

>bundle.eed39124e62c58ef34d2.js:37 DOMException: Nie można odczytać właściwości „sessionStorage” z okna. Odmowa dostępu dla tego dokumentu. at t.storeInSessionStorage (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:16:136860 ) at new t (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:69:20103 ) at ci (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:44115 ) at Eo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:58728 ) at jo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:65191 ) at Nr (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:84692 ) at Or (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:85076 ) at Ss (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91750 ) at vs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91130 ) at hs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:90151 )

Interfejs użytkownika używa magazynu sesji przeglądarki do przechowywania pewnych wartości właściwości do ładowania strony głównej. Aby było to potrzebne, w przeglądarce tej witryny muszą być dozwolone pliki cookie innych firm. Błąd wskazuje, że interfejs użytkownika nie może uzyskać dostępu do magazynu sesji. Występują dwa scenariusze tego problemu:

1.  Otwierasz interfejs użytkownika w trybie incognito w przeglądarce Edge/Chrome, a pliki cookie innych firm w trybie incognito są blokowane.
2.  Pliki cookie innych firm zostały zablokowane w Edge/Chrome.

### <a name="mitigation"></a>Sposób minimalizacji
Pliki cookie innych firm muszą być dozwolone w ustawieniach przeglądarki.

### <a name="google-chrome-browser"></a>Przeglądarka Google Chrome
1. opcja:
1.  Przejdź do ustawień, wpisując w pasku adresu chrome://settings/, a następnie przejdź do sekcji Prywatność i bezpieczeństwo -> Pliki cookie i inne dane witryny.
2.  Wybierz opcję Zezwalaj na wszystkie ciastka. Jeśli tego nie chcesz, przejdź do drugiej opcji.

Druga opcja:
1.  Przejdź do ustawień, wpisując w pasku adresu chrome://settings/, a następnie przejdź do sekcji Prywatność i bezpieczeństwo -> Pliki cookie i inne dane witryny.
2.  Jeśli jest wybrana opcja Zablokuj pliki cookie innej firmy w opcji Incognito” lub „Zablokuj pliki cookie innych firm”, przejdź do witryny Sites, która zawsze może używać ciastek, i kliknij przycisk **Dodaj**. 
3.  Dodaj nazwę witryny aplikacji Finanse & Operations - https://<your_FinOp_instance>.cloudax.dynamics.com. Upewnij się, że zaznaczysz pole wyboru „Wszystkie ciastka, tylko w tej witrynie”. 

### <a name="microsoft-edge-browser"></a>Przeglądarka Microsoft Edge
1.  Przejdź do ustawień -> uprawnienia do witryny -> pliki cookie i dane witryny.
2.  Wyłącz opcję Zablokuj pliki cookie innych firm.  

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Jak odłączyć i połączyć inne środowisko Dataverse z aplikacji finansowych i operacyjnych

**Wymagana rola do rozłączenia środowiska:** administrator systemu dla każdej aplikacji finansowej i operacyjnej lub Dataverse.

1. Zaloguj się do aplikacji finansowych i operacyjnych.
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

## <a name="how-to-ensure-data-integration-is-using-the-most-current-finance-and-operations-schema"></a>Jak zapewnić, by integracja danych odbywała się z wykorzystaniem najbardziej aktualnego schematu w aplikacji finansowych i operacyjnych

Możesz napotkać problemy z danymi podczas integracji danych, jeśli nie jest używany najbardziej aktualny schemat. Poniższe kroki pomogą ci odświeżyć listę encji w aplikacjach finansowych i operacyjnych oraz encji w Integratorze danych.

### <a name="refresh-entity-list-in-finance-and-operations-environment"></a>Odśwież listę podmiotów w środowisku aplikacji finansowych i operacyjnych
1.  Zaloguj się do swojego środowiska finansów i operacji.
2.  Wybierz pozycję **Zarządzanie danymi**.
3.  W sekcji Zarządzanie danymi wybierz **Ustawienia ramowe**.
4.  Na stronie **Parametry importu/eksportu danych** wybierz **Ustawienia jednostki**, a następnie wybierz pozycję **Odśwież listę jednostek**. Odświeżenie może zająć więcej niż 30 minut, w zależności od liczby zaangażowanych podmiotów.
5.  Przejdź do **Zarządzania danymi** i wybierz **Elementy danych**, aby sprawdzić, czy na liście znajdują się oczekiwane przez ciebie elementy. Jeśli na liście nie ma oczekiwanych encji, sprawdź, czy są one obecne w twoim środowisku aplikacji finansowych i operacyjnych i w razie potrzeby przywróć brakujące encje.

#### <a name="if-the-refresh-fails-to-resolve-the-issue-delete-and-re-add-the-entities"></a>Jeśli odświeżanie nie powiedzie się, usuń i dodaj ponownie encje

> [!NOTE]
> Przed usunięciem konieczne może się okazać zatrzymanie grup przetwarzania, które aktywnie korzystają z tych encji.

1.  Wybierz pozycję **Zarządzanie danymi** w środowisku aplikacji finansowych i operacyjnych i wybierz **Encje danych**.
2.  Wyszukaj encje, w których występują problemy, i zanotuj docelową encję, tabelę etapu, nazwę encji i inne ustawienia. Usuń encję lub encje z listy.
3.  Wybierz **Nowa** i ponownie dodaj encję lub encje, używając danych z kroku 2. 

#### <a name="refresh-entities-in-data-integrator"></a>Odświeżanie encji w Integratorze danych
Zaloguj się do centrum administracyjnego Power Platform i wybierz **Integrację danych**. Otwórz projekt, w którym pojawiają się problemy, i wybierz **Odśwież encje**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Włączanie i zapisywanie śledzenia sieciowego w celu dołączeniu śledzenia do biletów pomocy technicznej

Aby rozwiązać niektóre problemy, zespół pomocy technicznej może chcieć przejrzeć zapisy zdarzeń sieci. Aby utworzyć śledzenie sieci, należy wykonać następujące kroki:

### <a name="google-chrome-browser"></a>Przeglądarka Google Chrome

1. Na otwartej karcie naciśnij klawisz **F12** lub wybierz pozycję **Narzędzia deweloperskie**, aby otworzyć narzędzia deweloperskie.
2. Otwórz kartę **Sieć** i wpisz **integ** w polu tekstowym filtru.
3. Uruchom scenariusz i obserwuj rejestrowane żądania.
4. Kliknij prawym przyciskiem myszy wpisy i wybierz polecenie **Zapisz wszystko jako HAR z zawartością**.

### <a name="microsoft-edge-browser"></a>Przeglądarka Microsoft Edge

1. Na otwartej karcie naciśnij klawisz **F12** lub wybierz pozycję **Narzędzia deweloperskie**, aby otworzyć narzędzia deweloperskie.
2. Otwórz kartę **Sieć**.
3. Uruchom scenariusz.
4. Naciśnij przycisk **Zapisz**, aby wyeksportować wyniki do HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

