---
title: Rozwiązywanie problemów z podwójnym zapisem w aplikacjach Finanse i Działania
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem podwójnego zapisu w aplikacjach Finanse i Działania.
author: RamaKrishnamoorthy
ms.date: 04/12/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 58b20e38269922203b54173509e31c5e6f30c25b
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2022
ms.locfileid: "8565974"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Rozwiązywanie problemów z podwójnym zapisem w aplikacjach Finanse i Działania

[!include [banner](../../includes/banner.md)]



Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami Finanse i Działania i Dataverse. Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem **podwójnego zapisu** w aplikacjach Finanse i Działania.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Nie możesz załadować modułu podwójnego zapisu w aplikacji Finanse i Działania

Jeśli nie można otworzyć strony **podwójnego zapisywania**, wybierając opcję **podwójnego zapisywania** w obszarze roboczym **zarządzanie danymi**, prawdopodobnie usługa integracji danych jest niemożliwa. Utwórz bilet pomocy technicznej, aby zażądać ponownego uruchomienia usługi integracji danych.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Błąd podczas próby utworzenia mapy nowej tabeli

**Wymagane poświadczenia w celu rozwiązania problemu:** Ten sam użytkownik, który skonfigurował podwójne zapisywanie.

Podczas próby skonfigurowania nowej tabeli na potrzeby podwójnego zapisu może pojawić się następujący komunikat o błędzie. Jedyny użytkownik, który może stworzyć mapę, jest użytkownikiem, który konfiguruje połączenie podwójnego zapisu.

*Kod stanu odpowiedzi nie wskazuje powodzenia: 401 (nieautoryzowany).*

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Błąd podczas otwierania interfejsu użytkownika z podwójnym zapisywaniem

Podczas próby uzyskania dostępu do podwójnego zapisu w obszarze roboczym **zarządzanie danymi** może zostać wyświetlony następujący komunikat o błędzie:

*login.microsoftonline.com odmówił połączenia.*

Aby rozwiązać ten problem, zaloguj się przy użyciu okna prywatnego w Microsoft Edge, w oknie incognito w Chromium lub w oknie incognito w usłudze Google Chrome. Należy również odblokować lub wyczyścić pliki cookie innych firm.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Błąd podczas łączenia środowiska w celu wykonania podwójnego zapisywania lub dodania nowego mapowania tabeli

**Wymagana rola, aby rozwiązać problem:** administrator systemu w aplikacjach Finanse i Działania oraz Dataverse.

Podczas łączenia lub tworzenia map może wystąpić następujący błąd:

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

Ten błąd może wystąpić, jeśli użytkownik nie ma wystarczających uprawnień, aby połączyć podwójny zapis lub utworzyć mapy. Ten błąd może również wystąpić, jeśli środowisko Dataverse zostało zresetowane bez odłączenia podwójnego zapisu. Każdy użytkownik z rolą administratora systemu w aplikacjach Finanse i Działania i Dataverse może łączyć środowiska. Tylko użytkownik instalujący połączenie podwójnego zapisu może dodawać nowe mapowania tabeli. Po zakończeniu instalacji każdy użytkownik z rolą administratora systemu może monitorować stan i edytować mapowania.

## <a name="error-when-you-stop-the-table-mapping"></a>Błąd podczas zatrzymania mapowania tabeli

Podczas próby zatrzymania mapowania tabeli może pojawić się następujący komunikat o błędzie:

*\[Zabroniony\], \[{„stan”: 403, „źródłowy”: „”, „komunikat”: „błąd wymiany tokenów: Użytkownik nie może uzyskać dostępu do połączenia dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx”}\]”. Serwer zdalny zwrócił błąd: (403) zabroniony.*

Ten błąd występuje, gdy połączone środowisko Dataverse jest niedostępne.

Aby rozwiązać ten problem, utwórz bilet dla zespołu integracji danych. Dołącz śledzenie sieci, aby zespół integracji danych mógł oznaczyć mapy jako **Nie uruchomione** na zapleczu.

## <a name="enable-parallel-processing-in-finance-and-operations-apps-to-improve-performance"></a>Umożliwienie przetwarzania równoległego w aplikacjach finansowych i operacyjnych w celu zwiększenia wydajności

Włączenie przetwarzania równoległego może skrócić czas potrzebny na zaimportowanie danych z aplikacji finansowych i operacyjnych do aplikacji angażujących klientów i Microsoft Dataverse. 

Aby włączyć przetwarzanie równoległe w aplikacjach finansowych i operacyjnych, należy wykonać następujące czynności.

1. Zaloguj się do swojego środowiska finansów i operacji.
2. Kliknij kolejno **Zarządzanie danymi > Ustawienia ramowe**.
3. Wybierz **pozycję Ustawienia jednostki** i wybierz **opcję Konfiguruj parametry wykonywania jednostki**.
4. Dodaj parametry przetwarzania równoległego:
    - **Liczba rekordów progu importu** — liczba rekordów, które muszą zostać spełnione, zanim będzie włączone przetwarzanie równoległe.
    - **Liczba zadań importu** — liczba wątków (zadań) uruchamianych równolegle.
5. Wybierz opcję **Zapisz**.


## <a name="errors-while-trying-to-start-a-table-mapping"></a>Błędy podczas próby uruchomienia mapowania tabeli

### <a name="unable-to-complete-initial-data-sync"></a>Nie można ukończyć początkowej synchronizacji danych

Podczas próby przeprowadzenia wstępnej synchronizacji danych może zostać wyświetlony komunikat o błędzie podobny do następującego:

*Nie można ukończyć wstępnej synchronizacji danych. Błąd: błąd podwójnego zapisu — Rejestracja wtyczki nie powiodła się: nie można zbudować metadanych wyszukiwania przy podwójnym zapisie. Odwołanie do obiektu błędu nie jest ustawione na wystąpienie obiektu.*

Podczas próby ustawienia tego stanu mapowania na **Uruchomione** może zostać wyświetlony ten komunikat o błędzie. Poprawka jest zależna od przyczyny błędu:

+ Jeśli mapowanie ma zależne mapowania, należy pamiętać, aby włączyć mapowania zależne tego mapowania tabeli.
+ Być może w mapowaniu brakuje kolumn źródłowych lub docelowych. Jeśli w aplikacji Finanse i Działania nie ma kolumny, należy wykonać kroki w sekcji [Problem związany z brakiem kolumn tabeli na mapach](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Jeśli w usłudze Dataverse brakuje pola, w mapowaniu należy kliknąć przycisk **Odśwież tabele**, tak aby kolumny były automatycznie wstawiane ponownie do mapowania.

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>Błąd niezgodności wersji i uaktualnienie rozwiązań podwójnego zapisu

Podczas próby wykonania mapowania tabeli mogą pojawić się następujące komunikaty o błędzie:

+ *Grupy klientów (msdyn_customergroups) : błąd podwójnego zapisu — niezgodność wersji rozwiązania Dynamics 365 for Sales 'Dynamics365Company'. Wersja: '2.0.2.10' Wymagana wersja: '2.0.133'*
+ Niezgodność wersji rozwiązania *Dynamics 365 for Sales 'Dynamics365FinanceExtended'. Wersja: '1.0.0.0' Wymagana wersja: '2.0.227'*
+ Niezgodność wersji rozwiązania *Dynamics 365 for Sales 'Dynamics365FinanceAndOperationsCommon'. Wersja: '1.0.0.0' Wymagana wersja: '2.0.133'*
+ Niezgodność wersji rozwiązania *Dynamics 365 for Sales 'CurrencyExchangeRates'. Wersja: '1.0.0.0' Wymagana wersja: '2.0.133'*
+ Niezgodność wersji rozwiązania *Dynamics 365 for Sales 'Dynamics365SupplyChainExtended'. Wersja: '1.0.0.0' Wymagana wersja: '2.0.227'*

Aby rozwiązać te problemy, należy zaktualizować rozwiązania podwójnego zapisu w Dataverse. Pamiętaj, aby uaktualnić do najnowszego rozwiązania, które pasuje do wymaganej wersji rozwiązania.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
