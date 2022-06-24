---
title: Ograniczenie dostępu do sklepu podczas testowania lub rozwoju
description: W tym artykule wyjaśniono, jak ograniczyć dostęp do sklepu Microsoft Dynamics 365 Commerce podczas wewnętrznego testowania lub testowania.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 77b652aafa6aea807ab11fe02209bc7de43fa446
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898891"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a>Ograniczenie dostępu do sklepu podczas testowania lub rozwoju

[!include [banner](../../includes/banner.md)]

W tym artykule wyjaśniono, jak ograniczyć dostęp do sklepu Microsoft Dynamics 365 Commerce podczas wewnętrznego testowania lub testowania.

## <a name="description"></a>opis

Podczas testowania wewnętrznego lub aktywnego testowania można ograniczyć dostęp do witryny, aby uniemożliwić użytkownikom zewnętrznym dostęp do opublikowanych stron sklepu.

## <a name="resolution"></a>Rozdzielczość

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a>Konfigurowanie Azure AD B2C przy użyciu standardowych przepływów użytkownika

Aby uzyskać informacje dotyczące konfigurowania Azure Active Directory B2C (Azure AD B2C) dla witryny e-commerce, zobacz temat [Konfigurowanie dzierżawy usług B2C w Commerce](../set-up-b2c-tenant.md).

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a>Ogranicz dostęp użytkowników do stron sklepu i zablokuj tworzenie nowych użytkowników

Aby ograniczyć użytkownikom dostęp do stron sklepu w Konstruktorze witryn portalu Commerce, wykonaj następujące kroki.

1. Przejdź do swojej witryny.
1. Wybierz **Strony**, a następnie wybierz stronę, dla których chcesz ograniczyć dostęp użytkownika.
1. Wybierz moduł lub gniazdo fragmentu, a następnie **Edytuj**.
1. W okienku właściwości wybierz opcję **Wymaga zalogowania**, a następnie wybierz opcję **Zakończ edytowanie**.
1. Wybierz opcję **Publikuj**.

Aby zablokować tworzenie nowych użytkowników Azure AD w tej części, wykonaj następujące kroki.

1. Przejdź do [portalu Azure](https://portal.azure.com/).
1. Wybierz aplikację Azure AD B2C utworzoną dla swojego dostępu do witryny.
1. W okienku nawigacji po lewej stronie wybierz pozycję **Przepływy użytkownika**.
1. U góry strony **Przepływy użytkowników** wybierz **Nowy przepływ użytkowników**.
1. Na stronie **Wybierz typ przepływu użytkownika** wybierz pozycję **Podgląd**.
1. W środku strony wybierz pozycję **Zaloguj się w wersji 2**. Następnie wykonaj kroki w witrynie [Konfigurowanie dzierżawy usług B2C w Commerce](../set-up-b2c-tenant.md), aby skonfigurować przepływ jako standardowy przepływ użytkownika dla usługi Azure AD B2C w witrynie podczas testowania lub rozwoju.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w module Commerce](../set-up-b2c-tenant.md)

[Konfiguracja stron niestandardowych do logowań użytkowników](../custom-pages-user-logins.md)
