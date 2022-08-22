---
title: Zarządzanie użytkownikami i rolami e-Commerce
description: W tym artykule opisano sposób udzielania użytkownikom dostępu do środowiska tworzenia witryny Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 180fc5c0a9c9e247d5bd6ec7f469f313463526df
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279510"
---
# <a name="manage-e-commerce-users-and-roles"></a>Zarządzanie użytkownikami i rolami e-Commerce


[!include [banner](includes/banner.md)]

W tym artykule opisano sposób udzielania użytkownikom dostępu do środowiska tworzenia witryny Microsoft Dynamics 365 Commerce.

Aby ułatwić kontrolowanie dostępu użytkowników i przyznawanie użytkownikom uprawnień do wykonywania konkretnych zadań, środowisko tworzenia witryn używa grup zabezpieczeń utworzonych w Microsoft Azure Active Directory (Azure AD). Najpierw należy przypisać nową lub istniejącą grupę zabezpieczeń Azure AD do każdej roli w środowisku tworzenia treści. Następnie należy przyznać lub odebrać uprawnienia indywidualnym użytkownikom, dodając tych użytkowników do odpowiedniej grupy zabezpieczeń lub usuwając je z grupy zabezpieczeń.

## <a name="overview-of-roles-in-the-authoring-environment"></a>Omówienie ról w środowisku tworzenia

Środowisko tworzenia Dynamics 365 for Commerce obsługuje następujące role:

| Rola                 | Opis |
|----------------------|-------------|
| Administrator systemu | Użytkownicy, którzy mają tę rolę, mają uprawnienia do wszystkich narzędzi oraz dla wszystkich ocen i przeglądów. Mogą również tworzyć witryny. |
| Administrator   | Użytkownicy, którzy mają tę rolę, mają uprawnienia do wszystkich narzędzi i RnR w danej strukturze witryny. |
| Producent Web         | Użytkownicy dysponujący tą rolą mogą tworzyć strony, fragmenty i szablony, przesyłać i zarządzać zasobami oraz wzbogacać produkty i kategorie. |
| Czytelnik               | Użytkownicy, którzy mają tę rolę, mogą wyświetlać strony, szablony, zasoby, fragmenty, układy i ustawienia, ale nie mogą wprowadzać zmian. |
| Moderator RnR        | Użytkownicy, którzy mają tę rolę, mogą moderować recenzje produktów. |

## <a name="system-administrator-role"></a>Rola administratora systemu

Podczas udostępniania Dynamics 365 Commerce w środowisku Microsoft Dynamics Lifecycle Services (LCS), użytkownik jest proszony o podanie grupy zabezpieczeń dla roli **Administratora systemu**. Ta rola jest następnie automatycznie stosowana do wszystkich witryn, które są tworzone w konfigurowanym środowisku. Grupę zabezpieczeń dla tej roli można aktualizować tylko w usługi LCS. Na stronie **Administracja witryny** dla wszystkich witryn jest ona wyświetlana w trybie tylko do odczytu i służy tylko do celów informacyjnych.

## <a name="administrator-role"></a>Rola administratora

Podczas tworzenia nowej witryny w module Commerce użytkownik jest monitowany o podanie grupy zabezpieczeń dla roli **Administratora**. Aby zapoznać się z omówieniem uprawnień udzielanych przez tę rolę, zajrzyj do tabeli wcześniej w tym artykule.

## <a name="add-or-update-security-groups"></a>Dodaj lub zaktualizuj grupy zabezpieczeń

Po utworzeniu witryny użytkownik będący w grupach zabezpieczeń skojarzonych z rolami **Administratora systemu** i **Administratora** może uzyskać dostęp do środowiska tworzenia tej witryny. Aby przypisać użytkowników do ról **Producent Web**, **Moderator RnR** i **Czytelnik**, należy przypisać do nich grupy zabezpieczeń. Aby dodać grupę zabezpieczeń do roli lub zaktualizować grupę zabezpieczeń, która jest aktualnie przypisana do roli, wykonaj następujące kroki.

1. Przejdź do strony, którą chcesz zaktualizować.
1. W module **Zarządzanie witryną** otwórz stronę **Zabezpieczenia**.
1. Wybierz rolę do zmodyfikowania.
1. Dodawanie grup zabezpieczeń do ról lub usuwanie grup zabezpieczeń z ról.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)

[Zagadnienia optymalizacji wyszukiwarki dla witryny](search-engine-optimization-considerations.md)

[Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
