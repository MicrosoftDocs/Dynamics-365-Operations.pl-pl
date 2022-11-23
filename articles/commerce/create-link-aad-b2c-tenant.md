---
title: Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure
description: W tym artykule opisano sposób tworzenia i łączenia z istniejącą dzierżawą Azure Active Directory (Azure AD) między firmami (B2C) w portalu Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 0aa12387f00ffc3dd10688c6385c7952f089ab12
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785298"
---
# <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Utwórz lub Połącz istniejącą dzierżawę B2C w usłudze Azure AD w portalu Azure

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób tworzenia i łączenia z dzierżawą Azure Active Directory (Azure AD) między firmami (B2C) w portalu Microsoft Azure. Aby uzyskać więcej informacji, zobacz temat [Samouczek: Tworzenie dzierżawy B2C Azure Active Directory](/azure/active-directory-b2c/tutorial-create-tenant).

Aby utworzyć lub połączyć się z istniejącą dzierżawą Azure AD B2C w Azure Portal, wykonaj następujące kroki.

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com/).
1. W menu portalu Azure wybierz polecenie **Utwórz zasób**. Należy pamiętać o użyciu subskrypcji i katalogu, który będzie połączony ze środowiskiem Commerce.

    ![Utwórz zasób w portalu Azure.](./media/B2CImage_1.png)

1. Przejdź do **Tożsamość \> Azure Active Directory B2C**.
1. Na stronie **Utwórz nowego B2C dzierżawę lub Połącz z istniejącą stroną dzierżawy**, Skorzystaj z jednej z poniższych opcji, która najlepiej pasuje do potrzeb firmy:

    - **Utwórz nową dzierżawę B2C Azure AD**: Ta opcja służy do utworzenia nowej dzierżawy B2C w usłudze Azure AD.
        1. Wybierz **Stwórz nową dzierżawę B2C Azure AD**.
        1. W obszarze **Nazwa organizacji** wprowadź nazwę organizacji.
        1. W obszarze **początkowa nazwa domeny** wprowadź początkową nazwę domeny.
        1. W przypadku **kraju lub regionu** wybierz kraj lub region.
        1. Wybierz przycisk **Utwórz**, aby utworzyć dzierżawę.

     ![Tworzenie nowej dzierżawy Azure AD.](./media/B2CImage_2.png)

     - **Połącz istniejącą dzierżawę B2C Azure AD z moją subskrypcją systemu Azure**: Tę opcję należy użyć, jeśli istnieje już dzierżawa B2C Azure AD, do której ma zostać utworzone łącze.
        1. Wybierz **łącze do istniejącej dzierżawy B2C Azure AD do mojej subskrypcji systemu Azure**.
        1. W **Dzierżawa B2C Azure AD** wybierz odpowiednią dzierżawę B2C. Jeśli w polu wyboru zostanie wyświetlona wiadomość „nie znaleziono dzierżawców B2C”, nie masz istniejącej uprawnionej dzierżawy B2C i będzie konieczne utworzenie nowej.
        1. W **Grupie zasobów** wybierz opcję **Utwórz nową**. Wprowadź **nazwę** grupy zasobów, która będzie zawierać dzierżawcę, wybierz **lokalizację grupy zasobów**, a następnie wybierz pozycję **Utwórz**.

    ![Wybierz łącze do istniejącej dzierżawy B2C Azure AD do subskrypcji systemu Azure.](./media/B2CImage_3.png)

1. Po utworzeniu nowego katalogu B2C Azure AD (może to chwilę potrwać) na pulpicie nawigacyjnym pojawi się łącze do nowego katalogu. To łącze spowoduje przekierowanie do strony „Witamy w B2C usługi Azure Active Directory”.

    ![Połącz z nowym katalogiem usługi Azure AD.](./media/B2CImage_4.png)

> [!NOTE]
> Jeśli masz wiele subskrypcji na koncie systemu Azure lub skonfigurowano dzierżawcę B2C bez łączenia z aktywną subskrypcją, transparent do **rozwiązywania problemów** poinformuje dzierżawcę o połączeniu z subskrypcją. Wybierz komunikat rozwiązywania problemów i postępuj zgodnie z instrukcjami, aby rozwiązać problem z subskrypcją.

Poniższy obraz przedstawia przykład transparentu B2C Azure AD **Rozwiązywanie problemów**.

![Ostrzeżenie pokazujące katalog, który nie ma aktywnej subskrypcji.](./media/B2CImage_5.png)

## <a name="next-steps"></a>Następne kroki

Aby kontynuować proces konfigurowania dzierżawy B2C w Commerce, przejdź do [Tworzenie aplikacji B2C](create-b2c-app.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md)

[Tworzenie aplikacji B2C](create-b2c-app.md)

[Tworzenie zasad przepływów użytkownika](create-user-flow-policies.md)

[Dodaj dostawców tożsamości społecznościowych (opcjonalnie)](add-social-identity-providers.md)

[Aktualizuj program Commerce Headquarters, używając nowych informacji o B2C Azure AD](update-hq-aad-b2c-info.md)

[Konfigurowanie dzierżawy B2C w module kreatora witryny Commerce](config-b2c-tenant-site-builder.md)

[Informacje dodatkowe o B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
