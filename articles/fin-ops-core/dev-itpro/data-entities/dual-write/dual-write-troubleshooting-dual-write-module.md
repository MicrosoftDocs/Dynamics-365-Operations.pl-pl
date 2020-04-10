---
title: Rozwiązywanie problemów z modułem podwójnego zapisu w aplikacjach Finance and Operations
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem podwójnego zapisu w aplikacjach Finance and Operations.
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
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172767"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Rozwiązywanie problemów z modułem podwójnego zapisu w aplikacjach Finance and Operations

[!include [banner](../../includes/banner.md)]



Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service. Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem **podwójnego zapisu** w aplikacjach Finance and Operations.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Nie można załadować modułu podwójnego zapisywania w aplikacji Finance and Operations

Jeśli nie można otworzyć strony **podwójnego zapisywania**, wybierając opcję **podwójnego zapisywania** w obszarze roboczym **zarządzanie danymi**, prawdopodobnie usługa integracji danych jest niemożliwa. Utwórz bilet pomocy technicznej, aby zażądać ponownego uruchomienia usługi integracji danych.

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a>Błąd podczas próby utworzenia mapowania nowej jednostki

**Wymagane poświadczenia w celu rozwiązania problemu:** administrator dzierżawy Azure AD

Podczas próby skonfigurowania nowej jednostki na potrzeby podwójnego zapisywania może pojawić się następujący komunikat o błędzie:

*Kod stanu odpowiedzi nie wskazuje powodzenia: 401 (nieautoryzowany)*

Ten błąd występuje, ponieważ tylko Administrator dzierżawy Azure AD może dodać nowe mapowanie jednostki.

Aby rozwiązać ten problem, zaloguj się w aplikacji Finance and Operations jako Administrator dzierżawy Azure AD. Należy również przejść do witryny sieci Web.PowerApps.com i ponownie sprawdź poprawność połączenia.

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Błąd podczas otwierania interfejsu użytkownika z podwójnym zapisywaniem

Podczas próby uzyskania dostępu do podwójnego zapisu w obszarze roboczym **zarządzanie danymi** może zostać wyświetlony następujący komunikat o błędzie:

*login.microsoftonline.com odmówił połączenia.*

Aby rozwiązać ten problem, zaloguj się przy użyciu okna prywatnego w Microsoft Edge, w oknie incognito w Chromium lub w oknie incognito w usłudze Google Chrome. Należy również odblokować lub wyczyścić pliki cookie innych firm.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Błąd podczas łączenia środowiska w celu wykonania podwójnego zapisywania lub dodania nowego mapowania jednostki

**Wymagane poświadczenia w celu rozwiązania problemu:** administrator dzierżawy Azure AD

Podczas łączenia lub tworzenia map może wystąpić następujący błąd:

*Kod stanu odpowiedzi nie wskazuje powodzenia: 403 (tokenexchange).<br> Identyfikator sesji: \<twój identyfikator sesji\><br> Identyfikator głównego działania: \<twój identyfikator działania głównego\>*

Ten błąd może wystąpić, jeśli użytkownik nie ma wystarczających uprawnień, aby połączyć podwójny zapis lub utworzyć mapy. Aby połączyć środowiska i dodać nowe mapowania jednostek, należy skorzystać z konta administratora dzierżawy Azure AD. Jednak po zakończeniu pracy instalatora można za pomocą konta innego niż administrator monitorować stan i edytować mapowania.

## <a name="error-when-you-stop-the-entity-mapping"></a>Błąd podczas zatrzymania mapowania jednostki

Podczas próby zatrzymania mapowania encji może pojawić się następujący komunikat o błędzie:

*\[Zabroniony\], \[{„stan”: 403, „źródłowy”: „”, „komunikat”: „błąd wymiany tokenów: Użytkownik nie może uzyskać dostępu do połączenia dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx”}\]”. Serwer zdalny zwrócił błąd: (403) zabroniony.*

Ten błąd występuje, gdy połączone środowisko Common Data Service jest niedostępne.

Aby rozwiązać ten problem, utwórz bilet dla zespołu integracji danych. Dołącz śledzenie sieci, aby zespół integracji danych mógł oznaczyć mapy jako **Nie uruchomione** na zapleczu.
