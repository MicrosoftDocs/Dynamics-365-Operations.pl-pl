---
title: Rozpoczęcie korzystania z usługi rachunku kosztów
description: Ten temat zawiera szczegółowe informacje dotyczące licencjonowania i instrukcje dotyczące instalacji dla usługi rachunku kosztów.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276952"
---
# <a name="get-started-with-the-cost-accounting-service"></a>Rozpoczęcie korzystania z usługi rachunku kosztów

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> Funkcje opisane w tym temacie są dostępne jako część prywatnej wersji zapoznawczej. Zawartość tego tematu i funkcjonalność, którą on opisuje, podlegają zmianie. Aby uzyskać więcej informacji dotyczących wydań wersji zapoznawczych, zobacz [Aktualizacje do jednej wersji usługi — często zadawane pytania](../../fin-ops-core/fin-ops/get-started/one-version.md).

Usługa rachunku kosztów umożliwia wielokrotne księgowanie zapasów w księgach rachunku kosztów, które zostały skonfigurowane. Poszczególne księgi rachunku kosztów są kojarzone z *konwencją*. Konwencja jest zbiorem następujących rodzajów zasad (polityki) rachunkowości:

- Obiekt kosztów
- Podstawa miary danych wejściowych
- Założenie przepływu kosztów
- Składnik kosztu

> [!NOTE]
> Nawet po włączeniu usługi rachunku kosztów nadal można księgować zapasy w Microsoft Dynamics 365 Supply Chain Management w zwykły sposób.

Usługa rachunku kosztów jest dodatkiem. Aby udostępnić swoje funkcje, należy je zainstalować z poziomu Microsoft Dynamics Lifecycle Services (LCS). Można więc ocenić ją w środowisku testowym przed włączeniem go w środowisku produkcyjnym.

Usługa rachunku kosztów nie obsługuje obecnie wszystkich funkcji zarządzania kosztem, które są wbudowane w Dynamics 365 Supply Chain Management. Dlatego ważne jest, aby ocenić, czy aktualnie zestaw funkcji jest obecnie dostępny i spełni wymagania użytkownika.

## <a name="licensing"></a>Licencjonowanie

Usługa rachunku kosztów jest licencjonowana wraz z standardowymi funkcjami księgowania zapasów, które są dostępne dla Supply Chain Management. Nie trzeba kupować dodatkowej licencji, aby móc skorzystać z usługi rachunku kosztów.

## <a name="install-the-add-in"></a>Instalacja aplikacji dodatkowych

> [!IMPORTANT]
> Aby można było korzystać z usługi rachunku kosztów, należy posiadać środowisko o wysokiej dostępności z włączonymi usługami LCS (a nie środowisko OneBox) i musi być uruchomione Dynamics 365 Supply Chain Management w wersji 10.0.11 lub nowszej.

Aby skorzystać z usługi rachunku kosztów, należy zainstalować dodatek usługi rachunku kosztów w Supply Chain Management w sposób opisany w poniższej procedurze.

1. Zaloguj się w LCS.

1. Przejdź do obszaru **Zarządzanie funkcjami w wersji zapoznawczej**.

1. Wybierz znak plus (**+**).

1. W polu **Kod** wprowadź swój klucz beta dla usługi rachunku kosztów. (Twój klucz powinien zostać dostarczony pocztą e-mail.)

1. Wybierz opcję **Odblokuj**.

1. Otwórz środowisko usługi LCS, w którym chcesz dodać usługę.

1. Przejdź do **Pełne szczegóły**.

1. Przewiń w dół do pozycji skróconej karty **Zarządzaj dodatkami środowiskowymi**.

1. Wybierz opcję **Zainstaluj nowy dodatek**.

1. Wybierz **Usługa rachunku kosztów**.

1. Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.

1. Wybierz **Zainstaluj**.

1. Na skróconej karcie **Dodatki środowiska** należy sprawdzić, czy jest instalowana usługa rachunku kosztów. Po kilku minutach stan powinien ulec zmianie z **Instalowane** na **Zainstalowane**. (Aby zobaczyć tę zmianę, konieczne może być odświeżenie strony.) W tym momencie usługa rachunku kosztów jest gotowa do użycia.

## <a name="set-up-the-integration"></a>Konfiguracja integracji

Aby skonfigurować integrację między usługą rachunku kosztów a Dynamics 365 Supply Chain Management:

1. Wybierz kolejno opcje **Administrowanie systemem > Obszary robocze > Zarządzanie funkcjami**.

1. Wybierz **Sprawdź, czy są aktualizacje**.

1. Otwórz kartę **Wszystkie** i wyszukaj funkcję o nazwie *Usługa rachunku kosztów*.

1. Wybierz **Włącz teraz**.

1. Przejdź do **Zarządzanie kosztami > Usługa rachunku kosztów > Konfiguracja > Prametry usługi rachunku kosztów > Prametry integracji**.

1. W polu **Identyfikator aplikacji** wprowadź następujący kod:<br> 08231eb2-a501-4edb-b3c5-aede5e5e0c3f

1. W polu **Punkt końcowy usługi danych** wprowadź następujący adres URL:<br>https://operationsdataservice.operations365.dynamics.com/

1. W polu **Punkt końcowy usługi rachunku kosztu** wprowadź następujący adres URL:<br>https://costaccountingservice.operations365.dynamics.com/

1. Usługa rachunku kosztów jest teraz gotowa do użycia.

## <a name="related-resources"></a>Powiązane zasoby

[Usługa rachunu kosztów — strona główna](cost-accounting-service-home.md)
