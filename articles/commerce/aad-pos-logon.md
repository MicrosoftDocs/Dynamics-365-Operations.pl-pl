---
title: Włącz uwierzytelnianie Azure Active Directory w celu autoryzacji w punkcie sprzedaży
description: W tym temacie wyjaśniono, jak skonfigurować środowisko logowania w punkcie sprzedaży dla rozwiązania Microsoft Dynamics 365 Commerce, aby korzystało z uwierzytelniania Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 234d19bb6659af07c65763e05671742b9581e244
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206686"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>Włącz uwierzytelnianie Azure Active Directory w celu logowania w punkcie sprzedaży
[!include [banner](includes/banner.md)]


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
> 
> Obecnie funkcja **Zastąpienie przez menedżera** nie obsługuje Azure AD jako metody uwierzytelniania. Identyfikator operatora i hasło są wymagane nawet wtedy, gdy Azure AD jest skonfigurowany jako metoda uwierzytelniania w celu zalogowania się w punkcie sprzedaży.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>Skojarz konto Azure AD z pracownikiem

Aby pracownik sklepu mógł skorzystać z konta Azure AD w celu zalogowania się do aplikacji punktu sprzedaży, konto Azure AD musi być skojarzone z tym pracownikiem.

Aby skojarzyć konto Azure AD z pracownikiem, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny** \> **Pracownicy** \> **Wszyscy pracownicy**.
1. Otwórz stronę szczegółów pracownika.
1. Następnie w okienku akcji na karcie **Commerce** w grupie **Tożsamość zewnętrzna** wybierz opcję **Powiązanie istniejącej tożsamości**.
1. W oknie dialogowym **używanie istniejącej tożsamości zewnętrznej** wybierz opcję **Wyszukaj przy użyciu poczty e-mail**, wprowadź adres e-mail Azure AD, a następnie wybierz opcję **Szukaj**.
1. Wybierz konto Azure AD, które jest zwracane, a następnie kliknij przycisk **OK**.

Pola **alias**, **nazwa UPN** i **zewnętrzny identyfikator podrzędny** na karcie **Commerce** na stronie Szczegóły pracownika zostaną wypełnione.

> [!NOTE]
> Po zaktualizowaniu rekordu pracownika, na przykład w przypadku skojarzenia nowego konta Azure AD, zmiany hasła lub aktualizacji książki adresowej pracownika, zaleca się uruchomienie harmonogramu dystrybucji **1060** (**Pracownicy**) w celu zsynchronizowania najnowszych informacji o pracownikach z kanałem. Dzięki temu aplikacja punktu sprzedaży może pobierać poprawne dane na potrzeby sprawdzania uwierzytelniania i autoryzacji użytkowników.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie funkcjonalności logowania rozszerzonego w aplikacjach MPOS i Cloud POS](extended-logon.md)

[Tworzenie profilu funkcji handlu detalicznego](retail-functionality-profile.md)

[Konfigurowanie pracownika](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)


[!INCLUDE[footer-include](../includes/footer-banner.md)]