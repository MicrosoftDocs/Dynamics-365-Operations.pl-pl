---
title: Włącz uwierzytelnianie Azure Active Directory w celu autoryzacji w punkcie sprzedaży
description: W tym temacie wyjaśniono, jak skonfigurować środowisko logowania w punkcie sprzedaży dla rozwiązania Microsoft Dynamics 365 Commerce, aby korzystało z uwierzytelniania Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 03/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: f030e8382627191dd32d855e15432fc85dca4bbd
ms.sourcegitcommit: 1789a78de1cbeac19d96767812df653a191c67e9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2020
ms.locfileid: "3100387"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>Włącz uwierzytelnianie Azure Active Directory w celu autoryzacji w punkcie sprzedaży
[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Wielu klientów korzystających z rozwiązania Microsoft Dynamics 365 Commerce używa również innych usług firmy Microsoft w chmurze, a także Azure Active Directory (Azure AD), które mogą służyć do zarządzania poświadczeniami użytkowników tych usług. W takich przypadkach klienci mogą chcieć używać tego samego konta Azure AD w różnych aplikacjach. W tym temacie wyjaśniono, jak skonfigurować środowisko logowania w punkcie sprzedaży dla rozwiązania Commerce , aby korzystało z uwierzytelniania Azure AD.

## <a name="configure-azure-ad-authentication"></a>Konfigurowanie dostawców uwierzytelniania Azure AD

Aby udostępnić metodę logowania Azure AD w punkcie sprzedaży dla sklepu, należy skonfigurować ustawienia profilu funkcji sklepu, a następnie zastosować te ustawienia dla klientów punktu sprzedaży.

Aby skonfigurować profil funkcji, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny** \> **Ustawienia kanału** \> **Ustawienia punktu sprzedaży** \> **Profile punktów sprzedaży** \> **Profile funkcji**.
1. Wybierz profil funkcji, który ma zostać zmieniony.
1. W skróconej karcie **funkcje** w sekcji **logowanie pracowników punktu sprzedaży** Zmień wartość w polu **Metoda uwierzytelniania logowania** z **identyfikator pracownika i hasło** na **Azure Active Directory**.

Domyślnie wszystkie profile funkcji używają **identyfikatora pracownika i hasła** jako metody uwierzytelniania w punkcie sprzedaży. Dlatego też należy zmienić wartość pola **metoda uwierzytelnienia logowania**, jeśli ma używać Azure AD. Ta zmiana będzie miała wpływ na każdy sklep detaliczny połączony z wybranym profilem funkcji.

Aby zastosować ustawienia do klientów punktu sprzedaży, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny** \> **Dane IT sprzedaży** \> **Harmonogram dystrybucji**.
1. Uruchom harmonogram dystrybucji **1070** (**Konfiguracja kanału**).

> [!NOTE]
> Uwierzytelnianie Azure AD wymaga połączenia z Internetem. Nie będzie działać, gdy punkt sprzedaży jest w trybie offline.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>Skojarz konto Azure AD z pracownikiem

Aby pracownik sklepu mógł skorzystać z konta Azure AD w celu zalogowania się do aplikacji punktu sprzedaży, konto Azure AD musi być skojarzone z tym pracownikiem.

Aby skojarzyć konto Azure AD z pracownikiem, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny** \> **Pracownicy** \> **Wszyscy pracownicy**.
1. Otwórz stronę szczegółów pracownika.
1. Następnie w okienku akcji na karcie **Commerce** w grupie **Tożsamość zewnętrzna** wybierz opcję **Powiązanie istniejącej tożsamości**.
1. W oknie dialogowym **używanie istniejącej tożsamości zewnętrznej** wybierz opcję **Wyszukaj przy użyciu poczty e-mail**, wprowadź adres e-mail Azure AD, a następnie wybierz opcję **Szukaj**.
1. Wybierz konto Azure AD, które jest zwracane, a następnie kliknij przycisk **OK**.

Pola **alias**, **nazwa UPN** i **zewnętrzny identyfikator podrzędny** na karcie **Commerce** na stronie Szczegóły pracownika zostaną wypełnione.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie funkcjonalności logowania rozszerzonego w aplikacjach MPOS i Cloud POS](extended-logon.md)

[Tworzenie profilu funkcji handlu detalicznego](retail-functionality-profile.md)

[Konfigurowanie pracownika](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)
