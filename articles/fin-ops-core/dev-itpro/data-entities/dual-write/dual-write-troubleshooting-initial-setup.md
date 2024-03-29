---
title: Rozwiązywanie problemów podczas konfiguracji początkowej
description: Ten artykuł zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas integracji podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d33fc6f4895b53f16cc6957a3a2fc6b1abe90a2f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289523"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Rozwiązywanie problemów podczas konfiguracji początkowej

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse. A dokładniej, ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas integracji podwójnego zapisu.

> [!IMPORTANT]
> Niektóre problemy z tego artykułu mogą wymagać roli administratora systemu lub poświadczeń administratora klienta usługi Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Nie można połączyć aplikacje finansowe i operacyjne z Dataverse

**Wymagana rola w celu konfiguracji podwójnego zapisu:** administrator systemu w aplikacjach finansowych i operacyjnych i Dataverse.

Błędy na stronie **Łącze konfiguracji do Dataverse** są zazwyczaj spowodowane niekompletnymi problemami z ustawieniami lub uprawnieniami. Upewnij się, że cała kontrola kondycji jest przekazana na stronie **Łącze konfiguracji do Dataverse**, jak to pokazano na poniższej ilustracji. Nie można połączyć się z podwójnym zapisywaniem, dopóki nie przejdzie cała kontrola kondycji.

![Pomyślne sprawdzenie kondycji.](media/health_check.png)

Aby połączyć środowiska aplikacji finansowych i operacyjnych i Dataverse, trzeba mieć poświadczenia administratora dzierżawy Azure AD. Po połączeniu środowiska użytkownicy mogą się logować przy użyciu swoich poświadczeń konta i aktualizować istniejące mapowanie tabeli.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Umożliwia znalezienie limitu liczby tabel prawnych lub firm, które mogą być połączone w celu wykonania podwójnego odpisu

Podczas próby włączenia map może pojawić się następujący komunikat o błędzie:

*Błąd podwójnego zapisywania — Rejestracja wtyczki nie powiodła się: [(nie można uzyskać mapy partycji Menedżera okien pulpitu projektu-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Błąd przekracza maksymalną liczbę partycji dozwoloną w mapowaniu Menedżera okien pulpitu-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)]. Wystąpił co najmniej jeden błąd.*

Bieżący limit czasu połączenia ze środowiskiem wynosi około 40 tabel prawnych. Ten błąd występuje podczas próby włączenia map, a więcej niż 40 tabel prawnych jest połączonych między środowiskami.

## <a name="connection-set-failed-while-linking-environment"></a>Błąd zestawu połączenia podczas łączenia środowiska

Podczas łączenia środowiska podwójnego zapisu akcja została zakończona komunikatem o błędzie:

*Zapisywanie zestawu połączeń nie powiodło się! Element z tym samym kluczem został już dodany.*

Funkcja podwójnego zapisu nie obsługuje wielu firm o tej samej nazwie. Na przykład w przypadku dwóch firm o nazwie „DAT” w Dataverse zostanie wyświetlony ten komunikat o błędzie.

Aby odblokować odbiorcę, usuń duplikaty rekordów z tabeli **cdm_company** w Dataverse. Ponadto, jeśli tabela **cdm_company** ma rekordy bez nazwy, usuń lub popraw te rekordy.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Błąd podczas otwierania strony podwójnego zapisu w aplikacjach finansowych i operacyjnych

Podczas próby połączenia środowiska Dataverse na potrzeby podwójnego zapisu może pojawić się następujący komunikat o błędzie:

*Kod stanu odpowiedzi nie wskazuje powodzenia: 404 (Nie znaleziono).*

Ten błąd występuje, gdy krok zgody aplikacji nie jest ukończony. Można sprawdzić, czy zgoda została udzielona, logując się do `portal.azure.com` przy użyciu konta administratora dzierżawy i sprawdzając, czy na liście aplikacji dla przedsiębiorstw usługi AAD jest wyświetlona aplikacja innej firmy z identyfikatorem `33976c19-1db5-4c02-810e-c243db79efde`. Jeśli nie, należy ponownie uruchomić krok zgody w sposób opisany w następnej sekcji.

### <a name="providing-app-consent"></a>Udzielanie zgody aplikacji

+ Uruchom następujący adres URL, używając poświadczeń administratora.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Naciśnij przycisk **Akceptuj**, aby wyrazić zgodę. Udzielasz zgody na zainstalowanie aplikacji (z `id=33976c19-1db5-4c02-810e-c243db79efde`) w swojej dzierżawie.
+ Ta aplikacja jest wymagana przez Dataverse do komunikowania się z aplikacjami finansowymi i operacyjnymi.

    ![Rozwiązywanie problemów z konfiguracją początkowe synchronizacji.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Jeśli to nie działa, uruchom adres URL w trybie prywatnym programu Microsoft Edge lub trybie incognito programu Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>Nie można wykryć środowiska aplikacji finansowych i operacyjnych

Może zostać wyświetlony następujący komunikat o błędzie:

*Środowisko aplikacji finansowych i operacyjnych \*\*\*.cloudax.dynamics.com nie jest wykrywalne*.

Istnieją dwie przyczyny, które mogą powodować, że środowisko nie będzie wykrywalne:

+ Zalogowany użytkownik nie znajduje się w tej samej dzierżawie co wystąpienie aplikacji finansowych i operacyjnych.
+ Istnieje kilka starszych wystąpień aplikacji finansowych i operacyjnych, które były hostowane przez firmę Microsoft i miały problem z wykrywaniem. Aby usunąć ten problem, zaktualizuj wystąpienie aplikacji finansowych i operacyjnych. Po każdej aktualizacji środowisko staje się wykrywalne.

## <a name="403-forbidden-error-while-connections-are-being-created"></a>Błąd 403 (Zabronione) podczas tworzenia połączeń

W ramach procesu łączenia podwójnego zapisu dwa połączenia Power Apps (znane również jako połączenia *Apihub*) są tworzone w imieniu użytkownika w połączonym środowisku Dataverse. Jeśli klient nie ma licencji na środowisko Power Apps, tworzenie połączeń ApiHub nie powiedzie się i zostanie wyświetlony błąd 403 (Zabronione). Oto przykład tabeli pełnego komunikatu o błędzie:

> NMSG=\[ie można skonfigurować środowiska podwójnego zapisu. Error Details:Kod stanu odpowiedzi nie wskazuje powodzenia: 403 (Zakazane). - Kod statusu odpowiedzi nie wskazuje na sukces: 403 (Forbidden).\] STACKTRACE=\[   at Microsoft.Dynamics.Integrator.ProjectManagementService.DualWrite.DualWriteConnectionSetProcessor.\<CreateDualWriteConnectionSetAsync\>d\_\_29.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\DualWrite\\DualWriteConnectionSetProcessor.cs:line 297 --- End of stack trace from previous location where exception was thrown --- at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw() at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task) at Microsoft.Dynamics.Integrator.ProjectManagementService.Controllers.DualWriteEnvironmentManagementController.\<SetupDualWriteEnvironmentAsync\>d\_\_34.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\Controllers\\DualWriteEnvironmentManagementController.cs:line 265\]

Ten błąd występuje z powodu braku Power Apps licencji. Przypisz odpowiednią licencję (na przykład plan Power Apps Wersji próbnej 2) do użytkownika, aby użytkownik miał uprawnienia do tworzenia połączeń. Aby zweryfikować licencję, klient może przejść [do witryny Moje konto](https://portal.office.com/account/?ref=MeControl#subscriptions), aby wyświetlić licencje aktualnie przypisane do użytkownika.

Aby uzyskać więcej informacji o planach Power Apps, zobacz następujące artykuły:

- [Przypisz licencje użytkownikom](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide)
- [Zakup Power Apps dla organizacji](/power-platform/admin/signup-for-powerapps-admin)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

