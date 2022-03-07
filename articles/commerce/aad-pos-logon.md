---
title: Konfigurowanie uwierzytelniania Azure Active Directory w celu logowania w punkcie sprzedaży
description: W tym temacie opisano sposób konfigurowania Azure Active Directory jako metody uwierzytelniania w punkcie sprzedaży Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 9dfb0389b0ca4b2cf75ccc70f35824674e618055
ms.sourcegitcommit: dca3279a8b7cd5d0bcd4e4a3aa9938b337aa8849
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2021
ms.locfileid: "7402158"
---
# <a name="configure-azure-active-directory-authentication-for-pos-sign-in"></a>Konfigurowanie uwierzytelniania Azure Active Directory w celu logowania w punkcie sprzedaży

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania Azure Active Directory (Azure AD) jako metody uwierzytelniania w punkcie sprzedaży Microsoft Dynamics 365 Commerce.

Sprzedawcy detaliczni, którzy korzystają z rozwiązania Dynamics 365 Commerce oraz innych usług w chmurze firmy Microsoft, jak Microsoft Azure, Microsoft 365 i Microsoft Teams, na ogół chcą korzystać z Azure AD w celu centralizacji zarządzania poświadczeniami użytkowników w celu bezpiecznego i bezproblemowego logowania się między aplikacjami. Aby można było korzystać z uwierzytelniania Azure AD w punkcie sprzedaży Commerce, należy najpierw skonfigurować Azure AD jako metodę uwierzytelniania w centrali Commerce.

## <a name="configure-pos-authentication-method"></a>Konfigurowanie metody uwierzytelniania punktu sprzedaży

Aby skonfigurować metodę uwierzytelniania punktu sprzedaży w centrali Commerce, wykonaj następujące kroki.
    
1. Przejdź do opcji **Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji** i wybierz profil funkcji, który chcesz zmienić.
1. W sekcji **logowanie pracowników punktu sprzedaży** skróconej karty **Funkcje** wybierz żądaną opcję metody uwierzytelniania z listy rozwijanej **Metoda uwierzytelniania logowania**.

    Lista **Metoda uwierzytelniania logowania** zawiera trzy opcje:
    
    - **Identyfikator pracownika i hasło** — Ta opcja domyślna wymaga, aby użytkownicy punktu sprzedaży wprowadzali identyfikator pracownika i hasło, aby logować się do punktu sprzedaży i uzyskać dostęp do funkcji zastępowania menedżera.
    - **Azure AD bez jednokrotnego logowania** — ta opcja wymaga, aby użytkownicy punktu sprzedaży używali poświadczeń Azure AD w celu logowania się do punktu sprzedaży i uzyskania dostępu do funkcji zastępowania menedżera. Gdy klient punktu sprzedaży zostanie odświeżony lub otwarty ponownie, użytkownik punktu sprzedaży musi podać poświadczenia Azure AD, aby ponownie się zalogować.
    - **Azure AD z jednokrotnym logowaniem** — po wybraniu tej opcji użytkownicy punktu sprzedaży będą mogli zalogować się do programu Cloud POS (CPOS) przy użyciu aktywnych poświadczeń Azure AD, które są używane przez inne aplikacje sieci Web w tej samej przeglądarce sieci Web, lub logować się do programu Modern POS (MPOS) przy użyciu poświadczeń Azure AD używanych do logowania do systemu Windows. Obie metody umożliwiają logowanie bez konieczności wprowadzania poświadczeń Azure AD na ekranie logowania punktu sprzedaży. Dostęp do funkcji zastępowania menedżera punktu sprzedaży będzie jednak wciąż wymagał logowania przy użyciu poświadczeń Azure AD.

1. Aby zsynchronizować najnowsze ustawienia profilu funkcji z klientami punktu sprzedaży, wybierz opcje **Retail i Commerce > Retail i Commerce — składniki IT > Harmonogram dystrybucji** i uruchom zadanie **1070 (Konfiguracja kanału)**.

> [!NOTE]
> - Opcja metody uwierzytelniania **Azure AD bez jednokrotnego logowania** zastępuje opcję **Azure Active Directory** używaną w Commerce w wersji 10.0.18 i starszych.
> - Uwierzytelnianie Azure AD wymaga aktywnego połączenia z Internetem i nie działa, gdy punkt sprzedaży jest w trybie offline.

## <a name="associate-azure-ad-accounts-with-pos-users"></a>Kojarzenie kont Azure AD z użytkownikami punktu sprzedaży

Aby użyć Azure AD jako metody uwierzytelniania punktu sprzedaży, należy skojarzyć konta Azure AD z użytkownikami punktu sprzedaży w centrali Commerce. 

Aby skojarzyć konta Azure AD z użytkownikami punktu sprzedaży w centrali Commerce, wykonaj poniższe kroki.
    
1. Wybierz kolejno opcje **Retail i Commerce > Pracownicy > Pracownicy** i otwórz rekord pracownika.
1. Następnie w okienku akcji na karcie **Commerce** w grupie **Tożsamość zewnętrzna** wybierz opcję **Powiązanie istniejącej tożsamości**. 
1. W oknie dialogowym **używanie istniejącej tożsamości zewnętrznej** wybierz opcję **Wyszukaj przy użyciu poczty e-mail**, wprowadź adres e-mail Azure AD, a następnie wybierz opcję **Szukaj**.
1. Wybierz konto Azure AD, które jest zwracane, a następnie kliknij przycisk **OK**.

Po wykonaniu tych kroków konfiguracji pola **alias**, **nazwa UPN** i **zewnętrzny identyfikator podrzędny** na karcie **Commerce** na stronie Szczegóły pracownika zostaną wypełnione.

Aby zsynchronizować najnowsze dane użytkownika punktu sprzedaży i konta Azure AD z kanałem, wybierz opcje **Retail i Commerce > Retail i Commerce — składniki IT > Harmonogram dystrybucji** i uruchom zadanie **1060 (Personel)**.

> [!NOTE]
> Dobrą praktyką jest, aby po zaktualizowaniu informacji o pracowniku, takich jak hasło, uprawnienie do punktu sprzedaży, skojarzone konto Azure AD lub książka adresowa pracownika w centrali Commerce, uruchomić zadanie **1060 (Personel)** w celu zsynchronizowania z kanałem najnowszych informacji o pracowniku. Dzięki temu klient punktu sprzedaży może pobierać poprawne dane na potrzeby sprawdzania uwierzytelniania i autoryzacji użytkowników.

## <a name="pos-lock-register-and-sign-out-with-azure-ad-authentication"></a>Blokowanie rejestru punktu sprzedaży i wylogowywanie się z uwierzytelnianiem Azure AD

Po skonfigurowaniu metody uwierzytelniania Azure AD do punktu sprzedaży mają miejsce następujące zdarzenia:

- Funkcja **Blokowanie rejestru** nie będzie dostępna w aplikacji punktu sprzedaży. 
- Funkcja **Automatyczna blokada** będzie zachowywać się tak samo jak funkcja **Automatyczne wylogowanie**.
- Jeśli użytkownik punktu sprzedaży wybierze opcję **Wyloguj się**, przy następnym uruchomieniu punktu sprzedaży zostanie poproszony o zalogowanie się za pomocą uwierzytelnień Azure AD, niezależnie od tego, czy jest włączone jednokrotne logowanie.

## <a name="manager-override-functionality-with-azure-ad-authentication"></a>Funkcja zastępowania menedżera za pomocą uwierzytelniania Azure AD

Jeśli w punkcie sprzedaży skonfigurowano uwierzytelnianie Azure AD, funkcja zastępowania menedżera spowoduje otwarcie okna dialogowego z monitem o poświadczenia Azure AD użytkownika menedżera. Gdy zostanie zatwierdzone logowanie menedżera, poświadczenia Azure AD menedżera zostaną porzucone i poświadczenia Azure AD poprzedniego użytkownika będą używane do kolejnych operacji w punkcie sprzedaży.

> [!NOTE]
> - W Commerce w wersji 10.0.18 i starszych funkcja zastępowania menedżera nie obsługuje funkcji Azure AD. Identyfikator operatora i hasło są wymagane nawet wtedy, gdy metoda uwierzytelniania Azure AD jest skonfigurowana do logowania się w punkcie sprzedaży.
> - W przypadku używania CPOS z przeglądarką sieci Web Safari na urządzeniu z systemem iOS firmy Apple należy najpierw wyłączyć funkcję **Blokowanie wyskakujących okienek** w ustawieniach Safari, aby funkcja zastępowania menedżera działała z uwierzytelnieniem Azure AD. 

## <a name="security-best-practices-for-azure-ad-based-pos-authentication-on-shared-devices"></a>Najlepsze praktyki z zakresie zabezpieczeń dotyczące uwierzytelniania Azure AD w punkcie sprzedaży na wspólnych urządzeniach

Wielu sprzedawców detalicznych konfiguruje swoje środowisko sklepu detalicznego, tak aby wielu użytkowników musiało uzyskać dostęp do aplikacji punktu sprzedaży ze wspólnego urządzenia fizycznego. W tym kontekście podczas jednokrotnego logowania użytkownik może korzystać z wygodnego i bezproblemowego uwierzytelniania, ale może to również stwarzać lukę w zabezpieczeniach, jeśli bieżący użytkownik punktu sprzedaży nie zorientuje się, że korzysta z poświadczeń innego użytkownika do wykonywania transakcji lub operacji w punkcie sprzedaży. Przed skonfigurowaniem metody uwierzytelniania Azure AD do logowania do punktu sprzedaży zdecydowanie zaleca się przejrzenie zasad zabezpieczeń i ustawień logowania na wspólnych urządzeniach, aby określić, która opcja będzie najlepsza.

- Jeśli w środowisku sklepu jest używane wspólne konto (na przykład konto lokalne) na potrzeby logowania się na urządzeniu fizycznym, zalecane jest użycie opcji logowania **Azure AD bez jednokrotnego logowania**. Gwarantuje to, że każdy użytkownik punktu sprzedaży będzie jawnie podawał poświadczenia Azure AD, aby zalogować się do punktu sprzedaży.
- Jeśli w środowisku sklepu jest wymagane, aby pracownicy logowali się do punktu sprzedaży przy użyciu własnych kont Azure AD, i urządzenie fizyczne jest wspólne, zalecane jest użycie opcji logowania **Azure AD z jednokrotnym logowaniem**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie pracownika](tasks/worker.md)

[Tworzenie profilu funkcji handlu detalicznego](retail-functionality-profile.md)


[Konfigurowanie funkcjonalności logowania rozszerzonego w aplikacjach MPOS i Cloud POS](extended-logon.md)

[Najlepsze praktyki z zakresie zabezpieczeń dotyczące aplikacji Cloud POS w udostępnionych środowiskach](dev-itpro/secure-retail-cloud-pos.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
