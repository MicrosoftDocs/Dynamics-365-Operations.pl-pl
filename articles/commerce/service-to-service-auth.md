---
title: Konfigurowanie uwierzytelniania usługa-usługa
description: W tym artykule opisano, jak skonfigurować uwierzytelnianie między usługami w Microsoft Dynamics 365 Commerce, aby bezpiecznie wywoływać interfejsy API usług dla ocen i recenzji.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: e3134d4ddb2e4f3d260e51d49e7399ff84e0d74a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279456"
---
# <a name="configure-service-to-service-authentication"></a>Konfigurowanie uwierzytelniania usługa-usługa

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak skonfigurować uwierzytelnianie między usługami (S2S) w Microsoft Dynamics 365 Commerce, aby bezpiecznie wywoływać interfejsy programowania aplikacji (API) usługi na potrzeby ocen i recenzji.

Dynamics 365 Commerce oferuje [oceny i recenzje](ratings-reviews-overview.md) jako rozwiązanie wielokanałowe. To rozwiązanie umożliwia dostęp do interfejsów API usług spoza Commerce, umożliwiając wykonywanie różnych zadań. Do tych zadań należy importowanie ocen i przeglądów z zewnętrznego systemu do systemu Commerce oraz eksportowanie ocen i recenzji z aplikacji Commerce. Aby w programie Commerce można było w bezpieczny sposób wywołać oceny i przeglądać interfejsy API usług, należy najpierw skonfigurować uwierzytelnianie S2S, wykonując procedury w tym artykule.

## <a name="add-a-new-app-registration"></a>Dodaj nową rejestrację aplikacji

Aby można było dodać nową rejestrację aplikacji, musisz utworzyć aplikację za pomocą [portalu Azure](https://portal.azure.com). Aby zarejestrować aplikację w Azure Active Directory (Azure AD) i włączyć uwierzytelnianie, wykonaj kroki opisane w [Użyj Azure Active Directory z niestandardowym łącznikiem w Power Automate](/connectors/custom-connectors/azure-active-directory-authentication).

Zbierz następujące identyfikatory z portalu Azure. Te identyfikatory będą potrzebne w poniższych krokach.

- Identyfikator aplikacji klienta
- Identyfikator katalogu klienta (dzierżawcy)

Aby dodać nową rejestrację aplikacji w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Ustawienia**.
1. W **obszarze Uwierzytelnianie usługa-usługa (S2S)** wybierz pozycję **Zarządzaj**.

    ![Zarządzaj przyciskami w sekcji Uwierzytelnianie usługa-usługa (S2S) w Konstruktorze witryn w portalu Commerce.](media/Ratings-reviews-settings-service-to-service-authentication.png)

1. W okienku **Wpisy aplikacji S2S** wyświetlanym po prawej stronie wybierz pozycję **Dodaj nową rejestrację aplikacji S2S**.
1. W oknie dialogowym **Dodaj wpis aplikacji S2S** wprowadź następujące informacje. Użyj wartości z rejestracji aplikacji Azure.

    - **Nazwa** – Wprowadź nazwę swojej aplikacji (na przykład **Aplikacja Fabrikam**).
    - **Identyfikator aplikacji klienta** – Wprowadź identyfikator aplikacji (na przykład **00000000-0000-0000-0000-000000000000**).
    - **Identyfikator katalogu (dzierżawcy)** — umożliwia wprowadzenie identyfikatora katalogu (na przykład **00000000-0000-0000-0000-000000000000**).

    ![Okno dialogowe Dodaj wpis aplikacji S2S w narzędziu do tworzenia witryn handlowych.](media/Ratings-reviews-settings-S2S-APP-entry.png)

1. Wybierz opcję **Prześlij**. Nazwa Twojej aplikacji powinna pojawić się na liście w okienku **Wpisy aplikacji S2S**.
1. Zamknij okienko **Wpisy aplikacji S2S**.
1. Wybierz opcję **Zapisz**.

## <a name="edit-an-existing-app-registration"></a>Edytuj istniejącą rejestrację aplikacji

Aby edytować istniejącą rejestrację aplikacji w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Ustawienia**.
1. W **obszarze Uwierzytelnianie usługa-usługa (S2S)** wybierz pozycję **Zarządzaj**.
1. W okienku **Wpisy aplikacji S2S** wybierz symbol symbolu symboli obok wpisu, który chcesz edytować.
1. W razie potrzeby zaktualizuj wartości w polach **Nazwa**, **Identyfikator aplikacji klienta** i **Identyfikator katalogu (Dzierżawca)**.
1. Wybierz opcję **Prześlij**.
1. Zamknij okienko **Wpisy aplikacji S2S**.
1. Wybierz opcję **Zapisz**.

## <a name="remove-an-existing-app-registration"></a>Usuń istniejącą rejestrację aplikacji

Aby usunąć istniejącą rejestrację aplikacji w narzędziu do tworzenia witryn handlowych, wykonaj następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Ustawienia**.
1. W **obszarze Uwierzytelnianie usługa-usługa (S2S)** wybierz pozycję **Zarządzaj**.
1. W okienku **Wpisy aplikacji S2S** wybierz symbol kosza obok wpisu, który chcesz usunąć. Wpis zostanie usunięty z listy.
1. Zamknij okienko **Wpisy aplikacji S2S**.
1. Wybierz opcję **Zapisz**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zgoda na korzystanie z ocen i recenzji](opt-in-ratings-reviews.md)

[Zarządzanie ocenami i recenzjami](manage-reviews.md)

[Konfigurowanie ocen i recenzji](configure-ratings-reviews.md)

[Synchronizacja ocen produktów](sync-product-ratings.md)

[Włączanie ręcznego publikowania ocen i recenzji przez moderatora](manual-publish-rating-reviews.md)

[Importowanie i eksportowanie klasyfikacji oraz przeglądów](import-export-reviews.md)

[Oceny i recenzje — często zadawane pytania](ratings-reviews-faq.md) 
