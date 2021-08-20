---
title: Wprowadzenie do Globalnego księgowania zapasów
description: W tym temacie opisano rozpoczęcie pracy z funkcją Globalnego księgowania zapasów.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 90fcbdc5c9dd4301225952d885794bd4d03ef825fd5590896be13eacfad1f979
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773303"
---
# <a name="get-started-with-global-inventory-accounting"></a>Wprowadzenie do Globalnego księgowania zapasów

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Globalne księgowanie zapasów pozwala na prowadzenie wielu kont inwentaryzacyjnych w utworzonych Globalnych księgach zapasów. Poszczególne księgi Globalnych ksiąg zapasów są kojarzone z *konwencją*. Konwencja jest zbiorem następujących rodzajów zasad (polityki) rachunkowości:

- Obiekt kosztów
- Podstawa miary danych wejściowych
- Założenie przepływu kosztów
- Składnik kosztu

> [!NOTE]
> Nawet po włączeniu usługi Globalnych ksiąg zapasów nadal można księgować zapasy w Microsoft Dynamics 365 Supply Chain Management w zwykły sposób.

Globalne księgowanie zapasów jest dodatkiem. Aby udostępnić swoje funkcje, należy je zainstalować z poziomu Microsoft Dynamics Lifecycle Services (LCS). Można więc ocenić ją w środowisku testowym przed włączeniem go w środowisku produkcyjnym.

Funkcja Globalnego księgowania zapasów nie obsługuje obecnie wszystkich funkcji zarządzania kosztami, które są wbudowane w Supply Chain Management. Dlatego ważne jest, aby ocenić, czy aktualnie zestaw funkcji jest obecnie dostępny i spełni wymagania użytkownika.

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>Jak uzyskać dostęp do publicznej wersji zapoznawczej Globalnego księgowania zapasów

> [!IMPORTANT]
> Aby korzystać z funkcji Globalnego księgowania zapasów, musisz mieć włączone środowisko usługi LCS o wysokiej dostępności (nie środowisko OneBox). Ponadto trzeba korzystać z Supply Chain Management w wersji 10.0.19 lub nowszej.

Aby zarejestrować się w publicznej wersji zapoznawczej Globalnego księgowania zapasów, wyślij identyfikator środowiska usługi LCS pocztą e-mail do [zespołu ds. globalnego księgowania zapasów](mailto:GlobalInvAccount@microsoft.com). Po zatwierdzeniu do programu, zespół wyśle do Ciebie wiadomość e-mail zawierającą klucz beta funkcji Globalnego księgowania zapasów oraz punkty końcowe usługi. Po otrzymaniu klucza wersji beta można [zainstalować ten dodatek](#install).

## <a name="licensing"></a>Licencjonowanie

Globalna księga zapasów jest licencjonowana wraz z standardowymi funkcjami księgowania zapasów, które są dostępne dla Supply Chain Management. Nie trzeba kupować dodatkowej licencji, aby móc skorzystać z usługi Globalnego księgowania zapasów.

## <a name="prerequisites"></a>Wymagania wstępne

### <a name="set-up-microsoft-power-platform-integration"></a>Ustaw integrację z programem Microsoft Power Platform

Aby można było włączyć funkcję dodatku, należy ją zintegrować z Microsoft Power Platform.

1. Otwórz środowisko usługi LCS, w którym chcesz dodać usługę.
1. Przejdź do **Pełne szczegóły**.
1. Wybierz przycisk **Integracja Power Platform**, a następnie wybierz **Konfiguracja**.
1. W oknie dialogowym **Ustawienia środowiska Power platform** zaznacz pole wyboru, a następnie wybierz opcję **Ustawienia**. Zwykle konfiguracja trwa od 60 do 90 minut.
1. Po zakończeniu konfigurowania środowiska Microsoft Power Platform na stronie jest przedstawiana nazwa środowiska. Ponadto w sekcji **Integracja Power Platform** pokazano oświadczenie, że  „Konfiguracja środowiska Power Platform jest ukończona”. Globalne księgowanie zapasów nie wymaga aplikacji do podwójnego zapisu.

Aby uzyskać więcej informacji, zobacz [Konfiguracja po wdrożeniu środowiska](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).

### <a name="set-up-dataverse"></a>Skonfiguruj Dataverse

Przed skonfigurowaniem Dataverse dodaj do dzierżawy zasady usługi Globalnego księgowania zapasów, wykonując następujące kroki.

1. Zainstaluj moduł Azure AD w Windows PowerShell v2 zgodnie z opisem w [Zainstaluj Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).
1. Uruchom następujące polecenie PowerShell.

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

Następnie utwórz użytkowników aplikacji Globalnego księgowania zapasów w Dataverse w następujący sposób.

1. Otwórz adres URL środowiska Dataverse.
1. Przejdź do **Ustawienia zaawansowane \> System \> Zabezpieczenia \> Użytkownicy** i utwórz użytkownika aplikacji. Użyj menu **Widok**, aby zmienić widok strony na *Użytkowników aplikacji*.
1. Wybierz pozycję **Nowy**.
1. Ustaw wartość w polu **Identyfikator aplikacji** na *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.
1. Wybierz pozycję **Przypisz rolę**, a następnie pozycję *Administrator systemu*. Jeśli istnieje rola o nazwie *Użytkownik Common Data Service* również ją zaznacz.
1. Powtórz poprzednie kroki, ale ustaw w polu **Identyfikator aplikacji** wartość *5f58fc56-0202-49a8-ac9e-0946b049718b*.

Aby uzyskać więcej informacji, zobacz [Utwórz użytkownika aplikacji](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

Jeśli domyślnym językiem instalacji Dataverse nie jest język angielski, należy wykonać następujące kroki.

1. Przejdź do **Ustawienia zaawansowane \> Administracja \> Języki**.
1. Wybierz *Język angielski* (*LanguageCode=1033*) i wybierz opcję **Zastosuj**.

## <a name="install-the-add-in"></a><a name="install"></a>Instalacja aplikacji dodatkowych

Wykonaj poniższe kroki, aby zainstalować dodatek, który umożliwi korzystanie z programu Globalne księgowanie zapasów.

1. Jak [uzyskać dostęp](#sign-up) do publicznej wersji zapoznawczej Globalnego księgowania zapasów.
1. Zaloguj się w [LCS](https://lcs.dynamics.com/Logon/Index).
1. Przejdź do obszaru **Zarządzanie funkcjami w wersji zapoznawczej**.
1. Wybierz znak plus (**+**).
1. W polu **Kod** wprowadź swój klucz beta dla usługi Globalnego księgowania zapasów. (Po zalogowaniu się musisz odbierać klucz wersji beta pocztą e-mail)
1. Wybierz opcję **Odblokuj**.
1. Otwórz środowisko usługi LCS, w którym chcesz dodać usługę.
1. Przejdź do **Pełne szczegóły**.
1. Przejdź do **Integracji Power Platform** i wybierz pozycję **Ustawienia**.
1. W oknie dialogowym **Ustawienia środowiska Power platform** zaznacz pole wyboru, a następnie wybierz opcję **Ustawienia**. Zwykle konfiguracja trwa od 60 do 90 minut.
1. Po zakończeniu konfigurowania środowiska Microsoft Power Platform na skróconej karcie **Dodatki środowiska** wybierz pozycję **Zainstaluj nowy dodatek**.
1. Wybierz **Globalne księgowanie zapasów**.
1. Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.
1. Wybierz **Zainstaluj**.
1. Na skróconej karcie **Dodatki środowiska** należy sprawdzić, czy jest instalowana usługa Globalnego księgowania zapasów. Po kilku minutach stan powinien ulec zmianie z *Instalowane* na *Zainstalowane*. (Aby zobaczyć tę zmianę, konieczne może być odświeżenie strony.) W tym momencie Globalnego księgowania zapasów jest gotowa do użycia.

## <a name="set-up-the-integration"></a>Konfiguracja integracji

Wykonaj poniższe kroki, aby skonfigurować integrację pomiędzy programem Globalnego księgowania zapasów i Supply Chain Management.

1. Zaloguj się do modułu Supply Chain Management.
1. Wybierz kolejno opcje **Administrowanie systemem \> Zarządzanie funkcjami**.
1. Wybierz **Sprawdź, czy są aktualizacje**.
1. Na karcie **Wszystkie** wyszukaj funkcję o nazwie *Globalne księgowanie zapasów*.
1. Wybierz **Włącz teraz**.
1. Przejdź do strony **Globalne księgowanie zapasów \> Konfiguracja \> Parametry globalnego księgowania zapasów \> Parametry integracji**.
1. W polach **Punkt końcowy usługi danych** i **Punkt końcowy globalnego księgowania zapasów** należy wpisać adresy URL z wiadomości e-mail, którą zespół ds. globalnego księgowania zapasów wysłał po zapisaniu się do podglądu.

Globalne księgowanie zapasów jest gotowe do użycia.
