---
title: Wprowadzenie do Globalnego księgowania zapasów
description: W tym artykule opisano rozpoczęcie pracy z funkcją Globalnego księgowania zapasów.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cbe6bff6fab96900b8bd4e112a8858363fff86d1
ms.sourcegitcommit: 9870b773a2ea8f5675651199fdbc63ca7a1b4453
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013563"
---
# <a name="get-started-with-global-inventory-accounting"></a>Wprowadzenie do Globalnego księgowania zapasów

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Globalne księgowanie zapasów pozwala na prowadzenie wielu kont inwentaryzacyjnych w utworzonych Globalnych księgach zapasów. Poszczególne księgi Globalnych ksiąg zapasów są kojarzone z *konwencją*. Konwencja jest zbiorem następujących rodzajów zasad (polityki) rachunkowości:

- Obiekt kosztów
- Podstawa miary danych wejściowych
- Założenie przepływu kosztów
- Składnik kosztu

> [!NOTE]
> Nawet po włączeniu usługi Globalnych ksiąg zapasów nadal można księgować zapasy w Microsoft Dynamics 365 Supply Chain Management w zwykły sposób.

Globalne księgowanie zapasów jest dodatkiem. Aby udostępnić swoje funkcje, należy je zainstalować z poziomu Microsoft Dynamics Lifecycle Services (LCS). Można więc ocenić ją w środowisku testowym przed włączeniem go w środowisku produkcyjnym.

Funkcja Globalnego księgowania zapasów nie obsługuje obecnie wszystkich funkcji zarządzania kosztami, które są wbudowane w Supply Chain Management. Dlatego ważne jest, aby ocenić, czy aktualnie zestaw funkcji jest obecnie dostępny i spełni wymagania użytkownika.

## <a name="how-to-get-the-global-inventory-accounting-add-in"></a><a name="sign-up"></a>Jak uzyskać dostęp do dodatku Globalnego księgowania zapasów

> [!IMPORTANT]
> Aby korzystać z funkcji Globalnego księgowania zapasów, musisz mieć włączone środowisko usługi LCS o wysokiej dostępności (nie środowisko OneBox). Ponadto trzeba korzystać z Supply Chain Management w wersji 10.0.19 lub nowszej.

### <a name="supply-chain-management-version-10019-to-10026"></a>Supply Chain Management w wersji 10.0.19 na 10.0.26

Aby zainstalować dodatek Global Inventory Accounting for Supply Chain Management w wersji od 10.0.19 do 10.0.26, należy rozpocząć od [zainstalowania dodatku](#install). Następnie wyślij identyfikator środowiska usługi LCS i nazwę firmy pocztą e-mail do zespołu [globalnego księgowania zapasów](mailto:GlobalInvAccount@microsoft.com). Zespół wyśle Ci wiadomość e-mail z informacjami o punktach końcowych usługi Globalnego księgowania zapasów.

### <a name="supply-chain-management-version-10027-and-later"></a>Supply Chain Management w wersji 10.0.27 i nowszych

Aby zainstalować dodatek Global Inventory Accounting for Supply Chain Management w wersji od 10.0.27 i nowszych, należy rozpocząć od [zainstalowania dodatku](#install). W tych wersjach systemu Supply Chain Management usługi Globalne księgowanie zapasów są ustawiane automatycznie, więc nie trzeba ich szukać ręcznie. Jeśli podczas konfigurowania dodatku wystąpią jakieś problemy, skontaktuj się z [zespołem globalnego księgowania zapasów](mailto:GlobalInvAccount@microsoft.com).

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

Aby uzyskać więcej informacji, zobacz temat [Włączanie po wdrożeniu środowiska](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="install-the-add-in"></a><a name="install"></a>Instalacja aplikacji dodatkowych

Wykonaj poniższe kroki, aby zainstalować dodatek, który umożliwi korzystanie z programu Globalne księgowanie zapasów.

1. Zaloguj się w [LCS](https://lcs.dynamics.com/Logon/Index).
1. Otwórz środowisko usługi LCS, w którym chcesz dodać usługę.
1. Przejdź do **Pełne szczegóły**.
1. Przejdź do **Integracji Power Platform** i wybierz pozycję **Ustawienia**.
1. W oknie dialogowym **Ustawienia środowiska Power platform** zaznacz pole wyboru, a następnie wybierz opcję **Ustawienia**. Zwykle konfiguracja trwa od 60 do 90 minut.
1. Po zakończeniu konfigurowania środowiska Microsoft Power Platform zaloguj się do [centrum administracyjnego platformy Power Platform](https://admin.powerplatform.microsoft.com), a następnie zainstaluj dodatek Globalne księgowanie zapasów, wykonując następujące kroki:
   1. Wybierz środowisko, w którym chcesz zainstalować dodatek.
   1. Wybierz **Aplikacje Dynamics 365**.
   1. Wybierz **Zainstaluj aplikację**.
   1. Wybierz pozycję **Księgowanie magazynu globalnego usługi Dynamics 365**.
   1. Wybierz przycisk **Dalej**, aby zainstalować.
1. Wróć do środowiska LCS. Na skróconej karcie **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.
1. Wybierz **Globalne księgowanie zapasów**.
1. Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.
1. Wybierz **Zainstaluj**.
1. Na skróconej karcie **Dodatki środowiska** należy sprawdzić, czy jest instalowana usługa Globalnego księgowania zapasów. Po kilku minutach stan powinien ulec zmianie z *Instalowane* na *Zainstalowane*. (Aby zobaczyć tę zmianę, konieczne może być odświeżenie strony.) W tym momencie Globalnego księgowania zapasów jest gotowa do użycia.

Jeśli domyślnym językiem instalacji Dataverse nie jest język angielski, należy wykonać następujące kroki:
1. Przejdź do **Ustawienia zaawansowane \> Administracja \> Języki**.
1. Wybierz *Język angielski* (*LanguageCode=1033*) i wybierz opcję **Zastosuj**.

## <a name="set-up-the-integration"></a>Konfiguracja integracji

Wykonaj poniższe kroki, aby skonfigurować integrację pomiędzy programem Globalnego księgowania zapasów i Supply Chain Management.

1. Zaloguj się do modułu Supply Chain Management.
1. Wybierz kolejno opcje **Administrowanie systemem \> Zarządzanie funkcjami**.
1. Wybierz **Sprawdź, czy są aktualizacje**.
1. Na karcie **Wszystkie** wyszukaj funkcję o nazwie *(wersja zapoznawcza) Globalne księgowanie zapasów*.
1. Wybierz **Włącz teraz**.
1. Przejdź do strony **Globalne księgowanie zapasów \> Konfiguracja \> Parametry globalnego księgowania zapasów \> Parametry integracji**.
1. W zależności od wersji programu Supply Chain Management należy wykonać jedną z poniższych czynności:
    - **Supply Chain Management w wersji 10.0.19 do 10.0.26**: W polach **Punkt końcowy usługi danych** i **Punkt końcowy globalnej ewidencji zapasów** wprowadź adresy URL, które zostały wysłane do Ciebie pocztą elektroniczną przez zespół ds. globalnej ewidencji zapasów (zob. również [Jak uzyskać dostęp do dodatku Globalnego księgowania zapasów](#sign-up)).
    - **Supply Chain Management w wersji 10.0.27** i nowsza: nie trzeba wprowadzać punktów końcowych, więc możesz pominąć ten krok.

Globalne księgowanie zapasów jest gotowe do użycia.
