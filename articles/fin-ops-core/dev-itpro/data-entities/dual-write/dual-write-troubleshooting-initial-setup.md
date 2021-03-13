---
title: Rozwiązywanie problemów podczas konfiguracji początkowej
description: Ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas integracji podwójnego zapisu.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: cfbc1ab3ef6d47f6ec2d8ca4ca4b8940784e6e49
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129988"
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

![Pomyślne sprawdzenie kondycji](media/health_check.png)

Aby połączyć środowiska Finance and Operations i Dataverse, trzeba mieć poświadczenia administratora dzierżawy Azure AD. Po połączeniu środowiska użytkownicy mogą się logować przy użyciu swoich poświadczeń konta i aktualizować istniejące mapowanie tabeli.

## <a name="error-when-you-open-the-link-to-dataverse-page"></a>Błąd podczas otwierania łącza do strony Dataverse

**Wymagane poświadczenia w celu rozwiązania problemu:** administrator dzierżawy Azure AD

Może pojawić się następujący komunikat o błędzie podczas otwierania strony **Łącze do Dataverse** w aplikacji Finance and Operations:

*Kod stanu odpowiedzi nie wskazuje powodzenia: 404 (Nie znaleziono).*

Ten błąd występuje, gdy krok zgody nie został ukończony. Aby sprawdzić, czy krok zgody został zakończony, zaloguj się do portal.Azure.com przy użyciu konta administratora dzierżawy Azure AD i sprawdź, czy strona trzecia o identyfikatorze **33976c19-1db5-4c02-810e-c243db79efde** jest na liście w Azure AD **Aplikacji przedsiębiorstwa**. Jeśli nie, musisz podać zgodę aplikacji.

Aby zapewnić zgodę aplikacji, wykonaj następujące kroki.

1. Otwórz następujący adres URL, używając poświadczeń administratora. Powinien zostać wyświetlony monit o zgodę.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Wybierz przycisk **Akceptuj**, aby wskazać, że wyrażasz zgodę na zainstalowanie aplikacji o identyfikatorze **33976c19-1db5-4c02-810e-c243db79efde** w dzierżawie.

    > [!TIP]
    > Ta aplikacja jest wymagana do łączenia Dataverse i aplikacji Finance and Operations. Jeśli występują problemy z tym krokiem, należy otworzyć przeglądarkę w trybie incognito (w usłudze Google Chrome) lub w trybie InPrivate ( w Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Sprawdź, czy dane firmy i zespoły podwójnego zapisywania są poprawnie skonfigurowane podczas łączenia

Aby zapewnić poprawne działanie funkcji podwójnego zapisywania, w środowisku Dataverse zostaną utworzone firmy wybrane podczas konfigurowania. Domyślnie te firmy są tylko do odczytu, a właściwość **IsDualWriteEnable** ma wartość **prawda**. Ponadto tworzony jest domyślny właściciel i zespół jednostki biznesowej będący właścicielem, który zawiera nazwę firmy. Przed włączeniem map należy sprawdzić, czy jest określony domyślny właściciel zespołu. Aby znaleźć tabelę **firmy (CDM\_Company)**, należy wykonać następujące kroki:

1. W aplikacji opartej na modelu w Dynamics 365 wybierz filtr w prawym górnym rogu.
2. Z listy rozwijanej wybierz **Firma**.
3. Wybierz opcję **Uruchom**, aby zobaczyć wyniki.
4. Umożliwia wybór firmy połączonej w przypadku skonfigurowania podwójnego zapisywania.
5. Sprawdź, czy w kolumnie **Domyślnego zespołu będącego właścicielem** znajduje się wartość. Na poniższej ilustracji kolumna **Domyślny zespół będący właścicielem** jest ustawiona na **USMF podwójnego zapisywania**.

    ![Weryfikowanie domyślnego zespołu będącego właścicielem](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Umożliwia znalezienie limitu liczby tabel prawnych lub firm, które mogą być połączone w celu wykonania podwójnego odpisu

Podczas próby włączenia map może pojawić się następujący komunikat o błędzie:

*Błąd podwójnego zapisywania — Rejestracja wtyczki nie powiodła się: \[(nie można uzyskać mapy partycji Menedżera okien pulpitu-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Błąd przekracza maksymalną liczbę partycji dozwoloną w mapowaniu Menedżera okien pulpitu-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\]. Wystąpił co najmniej jeden błąd.*

Bieżący limit czasu połączenia ze środowiskiem wynosi około 40 tabel prawnych. Ten błąd występuje podczas próby włączenia map, a więcej niż 40 tabel prawnych jest połączonych między środowiskami.
