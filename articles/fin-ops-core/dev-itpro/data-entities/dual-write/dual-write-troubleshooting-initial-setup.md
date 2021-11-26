---
title: Rozwiązywanie problemów podczas konfiguracji początkowej
description: Ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas integracji podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c9bf5d9017579b4207e09769cff38361442e3938
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781447"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Rozwiązywanie problemów podczas konfiguracji początkowej

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse. A dokładniej, ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas integracji podwójnego zapisu.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Nie można połączyć aplikacji Finance and Operations z Dataverse

**Wymagana rola w celu konfiguracji podwójnego zapisu:** administrator systemu w aplikacjach Finance and Operations i Dataverse.

Błędy na stronie **Łącze konfiguracji do Dataverse** są zazwyczaj spowodowane niekompletnymi problemami z ustawieniami lub uprawnieniami. Upewnij się, że cała kontrola kondycji jest przekazana na stronie **Łącze konfiguracji do Dataverse**, jak to pokazano na poniższej ilustracji. Nie można połączyć się z podwójnym zapisywaniem, dopóki nie przejdzie cała kontrola kondycji.

![Pomyślne sprawdzenie kondycji.](media/health_check.png)

Aby połączyć środowiska Finance and Operations i Dataverse, trzeba mieć poświadczenia administratora dzierżawy Azure AD. Po połączeniu środowiska użytkownicy mogą się logować przy użyciu swoich poświadczeń konta i aktualizować istniejące mapowanie tabeli.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Umożliwia znalezienie limitu liczby tabel prawnych lub firm, które mogą być połączone w celu wykonania podwójnego odpisu

Podczas próby włączenia map może pojawić się następujący komunikat o błędzie:

*Błąd podwójnego zapisywania — Rejestracja wtyczki nie powiodła się: [(nie można uzyskać mapy partycji Menedżera okien pulpitu projektu-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Błąd przekracza maksymalną liczbę partycji dozwoloną w mapowaniu Menedżera okien pulpitu-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)]. Wystąpił co najmniej jeden błąd.*

Bieżący limit czasu połączenia ze środowiskiem wynosi około 40 tabel prawnych. Ten błąd występuje podczas próby włączenia map, a więcej niż 40 tabel prawnych jest połączonych między środowiskami.

## <a name="connection-set-failed-while-linking-environment"></a>Błąd zestawu połączenia podczas łączenia środowiska

Podczas łączenia środowiska podwójnego zapisu akcja została zakończona komunikatem o błędzie:

*Zapisywanie zestawu połączeń nie powiodło się! Element z tym samym kluczem został już dodany.*

Funkcja podwójnego zapisu nie obsługuje wielu firm o tej samej nazwie. Na przykład w przypadku dwóch firm o nazwie „DAT” w Dataverse zostanie wyświetlony ten komunikat o błędzie.

Aby odblokować odbiorcę, usuń duplikaty rekordów z tabeli **cdm_company** w Dataverse. Ponadto, jeśli tabela **cdm_company** ma rekordy bez nazwy, usuń lub popraw te rekordy.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Błąd podczas otwierania strony podwójnego zapisu w aplikacjach Finance and Operations

Podczas próby połączenia środowiska Dataverse na potrzeby podwójnego zapisu może pojawić się następujący komunikat o błędzie:

*Kod stanu odpowiedzi nie wskazuje powodzenia: 404 (Nie znaleziono).*

Ten błąd występuje, gdy krok zgody aplikacji nie jest ukończony. Można sprawdzić, czy zgoda została udzielona, logując się do `portal.azure.com` przy użyciu konta administratora dzierżawy i sprawdzając, czy na liście aplikacji dla przedsiębiorstw usługi AAD jest wyświetlona aplikacja innej firmy z identyfikatorem `33976c19-1db5-4c02-810e-c243db79efde`. Jeśli nie, należy ponownie uruchomić krok zgody w sposób opisany w następnej sekcji.

### <a name="providing-app-consent"></a>Udzielanie zgody aplikacji

+ Uruchom następujący adres URL, używając poświadczeń administratora.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Naciśnij przycisk **Akceptuj**, aby wyrazić zgodę. Udzielasz zgody na zainstalowanie aplikacji (z `id=33976c19-1db5-4c02-810e-c243db79efde`) w swojej dzierżawie.
+ Ta aplikacja jest wymagana przez Dataverse do komunikowania się z aplikacjami Finance and Operations.

    ![Rozwiązywanie problemów z konfiguracją początkowe synchronizacji.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Jeśli to nie działa, uruchom adres URL w trybie prywatnym programu Microsoft Edge lub trybie incognito programu Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>Środowisko Finance and Operations nie jest wykrywalne

Może zostać wyświetlony następujący komunikat o błędzie:

*Środowisko aplikacji Finance and Operations \*\*\*.cloudax.dynamics.com nie jest wykrywalne.*

Istnieją dwie przyczyny, które mogą powodować, że środowisko nie będzie wykrywalne:

+ Zalogowany użytkownik nie znajduje się w tej samej dzierżawie co wystąpienie Finance and Operations.
+ Istnieje kilka starszych wystąpień Finance and Operations, które były hostowane przez firmę Microsoft i miały problem z wykrywaniem. Aby usunąć ten problem, zaktualizuj wystąpienie Finance and Operations. Po każdej aktualizacji środowisko staje się wykrywalne.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
