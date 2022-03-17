---
title: Konfigurowanie połączenia usługi SharePoint
description: W tym temacie wyjaśniono sposób konfigurowania połączenia, aby fakturowanie elektroniczne było dostępne w witrynie Microsoft SharePoint.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6b9fffc1f3525e69792517dd1c6ebdcfbe5a74d2
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371602"
---
# <a name="configure-a-sharepoint-connection"></a>Konfigurowanie połączenia usługi SharePoint

[!include [banner](../includes/banner.md)]

Usługa fakturowania elektronicznego może odczytywać pliki z folderów firmy Microsoft SharePoint i przekazywać pliki do SharePoint. Aby mieć pewność, że fakturowanie elektroniczne będzie mieć dostęp do określonej witryny SharePoint, należy podać poświadczenia witryny dla usługi fakturowania elektronicznego. Ponadto, aby zapewnić bezpieczne przechowywanie poświadczeń, nie podawaj ich bezpośrednio. Należy go zapisać w kluczu Azure i podać klucz tajny Azure Key Vault.

## <a name="grant-access-to-a-sharepoint-folder"></a>U przyznaj dostęp do folderu SharePoint

1. Utwórz rejestrację aplikacji w dzierżawie, w której zainstalowano usługę Regulatory Configuration Service (RCS).

    1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com/).
    2. Przejdź do **Rejestracje aplikacji**.
    3. Wybierz opcję **Nowa rejestracja**.
    4. Wprowadź nazwę, na przykład **Aplikacja SharePoint do fakturowania elektronicznego**, i dokończ rejestrację
    5. Wybierz nową rejestrację aplikacji.
    6. Na karcie **Uwierzytelnianie** włącz opcję **Zezwalaj na przepływy klienta publicznego**.
    4. Na karcie **Certyfikaty i kluczy tajnych** nowego klienta wybierz **Nowy klucz tajny klienta**, aby utworzyć klucz tajny klienta.
    5. Skopiuj wartość utworzonego klucza tajnego.

    Postępuj zgodnie z tymi wskazówkami:

    - Nie używaj tej samej rejestracji aplikacji dla różnych usług.
    - Postępuj zgodnie z zaleceniami [zasad dotyczących hasła](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide).
    - Ustawianie rotacji haseł. Podczas rotacji utwórz nowy klucz tajny klienta dla rejestracji aplikacji, zaktualizuj klucz, a następnie usuń stary klucz tajny.

2. Zapisz wartości **klucz tajny rejestracji aplikacji** i **identyfikator aplikacji (klienta)** jako dwa nowe klucze tajne w magazynie kluczy w konfiguracji środowiska fakturowania elektronicznego.
3. Dodaj utworzone wpisy tajne do parametrów Key Vault w konfiguracji środowiska fakturowania elektronicznego w RCS.
4. W portalu Azure udziel dostępu do programu SharePoint. Ten krok powinien zostać ukończony przez administratora dzierżawcy.

    1. Wybierz utworzoną rejestrację aplikacji.
    2. Na karcie **Uprawnienia do interfejsu API** wybierz opcję **Dodaj uprawnienie**.
    3. Wybierz **Microsoft graph (Uprawnienia do aplikacji)** \> **Sites.Selected**.
    4. Wybierz opcję **Ut dot. zgody administratora dla \<user&nbsp;name\>**.
    5. Przejrzyj pole **Stan**, aby upewnić się, że zostały przyznane uprawnienia.

        ![Uprawnienia przyznane na karcie Uprawnienia interfejsu API.](media/configured-permissions.jpg)

    6. Otwórz [Eksploratora wykresów — Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer) i zaloguj się.
    7. W lewym okienku, na karcie **Przykładowe zapytania**, w obszarze **Witryny SharePoint** wybierz pozycję Pobierz **witrynę SharePoint, opartą na względnej ścieżce witryny**.
    8. Wprowadź parametry **\{host-name\}** i **\{server-relative-path\}** Na przykład wypełnij nazwę  `<domain>.sharepoint.com` dla **\{host-name\}** i `sites/<siteName>` dla **\{server-relative-path\}**.

        > [!NOTE]
        > W przypadku domyślnej witryny internetowej pozostaw parametr **\{server-relative-path\}** pusty.

    9. Wybierz opcję **Uruchom kwerendę** i zapisz wynik.
    10. Skonfiguruj następującą kwerendę.

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        W tym zapytaniu **\{site-id\}** jest wartością węzła **id** z poprzedniej odpowiedzi na zapytanie.

        Oto treść żądania.

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        W treści żądania **\{app-id\}** to wartość **Identyfikator aplikacji (klienta)**, a **\{app-name\}** to wartość **Nazwa aplikacji** wartość.

        ![Zapytanie POST.](media/app-id-query.jpg)

    11. Na karcie **Modyfikuj uprawnienia** wybierz **Otwórz panel uprawnień**, a następnie wybierz **Witryny** \> **Sites.FullControl.All** \> **Zgody**.
    12. Wybierz **Wykonaj zapytanie**.

Usługa fakturowania elektronicznego ma teraz dostęp do Twojej witryny SharePoint.
