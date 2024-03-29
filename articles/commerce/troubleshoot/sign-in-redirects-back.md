---
title: Łącze logowania jest przekierowywany z powrotem do witryny handlu elektronicznego
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc przy przekierowywanym łączu logowania z powrotem do witryny handlu elektronicznego, a nie na stronę logowania.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 0bc9c0afbd6b349d8565f9eea56e207eae179f65
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291463"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a>Łącze logowania jest przekierowywany z powrotem do witryny handlu elektronicznego

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc przy przekierowywanym łączu logowania z powrotem do witryny handlu elektronicznego, a nie na stronę logowania.

## <a name="description"></a>opis

Po skonfigurowaniu nowej dzierżawy usługi Microsoft Azure Active Directory B2C (Azure AD B2C) w Konstruktorze witryn Commerce użytkownicy, którzy wybiorą łącze **Logowania**, są przekierowywani z powrotem do głównej strony docelowej witryny usługi handlu elektronicznego, bez konieczności logowania się do tej strony.

## <a name="resolution"></a>Rozdzielczość

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a>Potwierdź, że adres URL odpowiedzi jest poprawnie skonfigurowany w aplikacji Azure AD B2C

Aby potwierdzić, że adres URL odpowiedzi jest poprawnie skonfigurowany w aplikacji Azure AD B2C, wykonaj następujące kroki.

1. Przejdź do [portalu Azure](https://portal.azure.com/).
1. Wybierz aplikację Azure AD B2C utworzoną dla swojego dostępu do witryny.
1. Wybierz aplikację utworzoną podczas konfigurowania Azure AD B2C.
1. W obszarze **Adres URL odpowiedzi** upewnij się, że lista zawiera wpisy zarówno dla adresu URL domeny witryny, jak i adresu URL wygenerowanego w portalu e-commerce, jak pokazano na przykładzie na poniższej ilustracji.

    ![Wpisy adresu URL odpowiedzi Azure AD B2C.](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> Zarówno adres URL domeny witryny, jak i adres URL generowany przez e-commerce muszą mieć prawidłowy format adresu URL, który nie zawiera początkowych ani końcowych ukośników.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarejestruj połączoną aplikację sieci Web w Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[Konfigurowanie dzierżawy B2C w module Commerce](../set-up-b2c-tenant.md)
