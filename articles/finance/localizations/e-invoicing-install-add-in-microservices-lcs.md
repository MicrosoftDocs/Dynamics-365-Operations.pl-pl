---
title: Instalacja dodatku dla mikrousług w usłudze Lifecycle Services
description: W tym artykule wyjaśniono, jak zainstalować dodatek fakturowania elektronicznego w Microsoft Dynamics Lifecycle Services (LCS).
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 938b00192acc0ff5534239f2f280792471181fad
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710816"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Zainstaluj dodatek dla mikrousług w Lifecycle Services

[!include [banner](../includes/banner.md)]

Uwierzytelnianie w usłudze fakturowania elektronicznego wymaga zarejestrowania środowiska Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management na platformie usług poprzez zainstalowanie dodatku dla Twojego środowiska w Microsoft Dynamics Lifecycle Services (LCS).

Aby zarejestrować środowisko, wykonaj następujące kroki.

1. Zaloguj się do swojego konta LCS.
2. Na pulpicie projektu wybierz projekt LCS.
2. W projekcie, na pulpicie nawigacyjnym **Środowiska**, wybierz swoje wdrożone środowisko. Wybrane środowisko musi być uruchomione.
3. Na karcie **Integracja Power Platform** w sekcji **Dodatki środowiska** wybierz pozycję **Zainstaluj nowy dodatek**.
4. Wybierz **Fakturowanie elektroniczne**.
5. W polu **Identyfikator aplikacji AAD** wprowadź stałą wartość **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Ta wartość jest zawsze stałą wartością. Upewnij się, że jest wprowadzany tylko unikatowy identyfikator globalnie (GUID). Nie używaj żadnych innych symboli, takich jak spacje, przecinki, kropki czy cudzysłowy.
6. W polu **Identyfikator dzierżawy usługi AAD** wprowadź identyfikator dzierżawy konta subskrypcji systemu Azure. Dzierżawca Azure Active Directory (Azure AD) określony przez użytkownika powinien być dzierżawcą używanym dla usługi Regulatory Configuration Service (RCS).
7. Przejrzyj warunki, a następnie zaznacz pole wyboru.
8. Wybierz **Zainstaluj**. Po kilku minutach stan powinien ulec zmianie z **Instalowane** na **Zainstalowane**. Aby zobaczyć tę zmianę, może być konieczne odświeżenie strony.

Fakturowanie elektroniczne jest teraz gotowe do użycia.

> [!NOTE]
> Firmy zwykle mają kilka środowisk zarządzania finansami lub Supply Chain Management environments. Środowiska te obejmują środowiska produkcyjne, środowiska testów akceptacji użytkownika (UAT) oraz środowiska programistyczne (piaskownice). Musisz wykonać powyższą procedurę dla wszystkich środowisk, które chcesz połączyć z fakturowaniem elektronicznym.
