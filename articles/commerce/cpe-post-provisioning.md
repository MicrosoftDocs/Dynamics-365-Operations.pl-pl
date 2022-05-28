---
title: Konfigurowanie środowiska oceny rozwiązania Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.
author: psimolin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9738700ca495d54c91ad91aa9c5a3d32c95a5a5
ms.sourcegitcommit: 4a973ac0e7af0176270a8070a96a52293567dfbf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8747644"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a>Konfigurowanie środowiska oceny rozwiązania Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.

Procedury opisane w tym temacie należy wykonać dopiero po zakończeniu aprowizacji środowiska oceny usługi Commerce. Aby uzyskać informacje dotyczące sposobu aprowizowania środowiska oceny usługi Commerce, zobacz [Aprowizowanie środowiska oceny usługi Commerce](provisioning-guide.md).

Po zakończeniu kompleksowej aprowizacji środowiska oceny usługi Commerce wykonać dodatkowe czynności konfiguracyjne po aprowizacji, aby można było rozpocząć ocenę środowiska. Aby wykonać te kroki, należy użyć usług Microsoft Dynamics Lifecycle Services (LCS) i Dynamics 365 Commerce.

## <a name="before-you-start"></a>Przed rozpoczęciem

1. Zaloguj się do [portalu usługi LCS](https://lcs.dynamics.com).
1. Przejdź do projektu.
1. W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.
1. Wybierz swoje środowisko na liście.
1. W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do środowiska**. Nastąpi wysłanie do modułu Commerce Headquarter.
1. Upewnij się, że wybrano firmę **USRT** w prawym górnym rogu.
1. Przejdź do pozycji **Parametry Commerce \> Konfigurowanie parametrów** i upewnij się, że istnieje wpis **ProductSearch.UseAzureSearch** ustawiony na **true**. Jeśli brakuje tego wpisu, możesz go dodać, ustawić wartość na **true**, a następnie wybrać **Baza danych kanałów \> Pełna synchronizacja danych** dla Commerce Scale Unit powiązanej z Twoją witryną handlu elektronicznego.
1. Przejdź do **Handel detaliczny i inny \> Ustawienia Headquarters \> Harmonogram handlu \> Zainicjuj harmonogram handlu**. W menu **Inicjowanie harmonogramu handlu** upewnij się, że opcja **Usuń istniejącą konfigurację** jest ustawiona na wartość **Tak**, a następnie kliknij przycisk **OK**.
1. Aby dodać kanały do modułu Commerce Scale Unit, przejdź do **Sprzedaż detaliczna i handel \> Konfiguracja centrali \> Harmonogram handlu \> Baza danych kanałów**, a następnie w lewym panelu wybierz moduł Commerce Scale Unit. Na skróconej karcie **kanału sprzedaży** detalicznej dodaj **sklep internetowy AW**, **sklep internetowy AW Business** i rozszerzone kanały **sklepu internetowego firmy Fabrikam**. Opcjonalnie można dodać sklepy sieci sprzedaży, jeśli będzie korzystać z aplikacji POS (na przykład **Seattle**, **San Francisco** i **San Jose**).

Podczas wykonywania działań związanych z inicjowaniem obsługi administracyjnej w module Commerce Headquarter należy się upewnić, że firma **USRT** jest zawsze zaznaczona.

## <a name="configure-the-point-of-sale"></a>Konfigurowanie punktu sprzedaży

### <a name="associate-a-worker-with-your-identity"></a>Kojarzenie pracownika z Twoją tożsamością

Aby skojarzyć pracownika z tożsamością, wykonaj następujące kroki w Commerce Headquarters.

1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Pracownicy etatowi \> Pracownicy**.
1. Na liście znajdź i wybierz następujący rekord: **000713 - Andrew Collette**.
1. W okienku akcji wybierz **Commerce**.
1. Wybierz pozycję **Skojarz istniejącą tożsamość**.
1. W polu **Adres e-mail** na prawo od pola **Wyszukaj, używając poczty e-mail** wprowadź swój adres e-mail.
1. Wybierz opcję **Wyszukaj**.
1. Wybierz rekord ze swoją nazwą.
1. Kliknij przycisk **OK**.
1. Wybierz opcję **Zapisz**.

### <a name="activate-cloud-pos"></a>Aktywować punkt sprzedaży w chmurze

Aby aktywować punkt sprzedaży chmury, wykonaj następujące kroki w usłudze LCS.

1. W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.
1. Wybierz swoje środowisko na liście.
1. W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do punktu sprzedaży w chmurze**.
1. Wybierz przycisk **Dalej**, aby otworzyć okno dialogowe **Przed rozpoczęciem**.
1. Pole **Serwer URL** powinno pozostać niezmienione. Wybierz pozycję **Następny**.
1. Zaloguj się przy użyciu konta usługi Microsoft Azure Active Directory (Azure AD).
1. W polu **Nazwa sklepu** wybierz opcję **San Francisco**, a następnie wybierz przycisk **Dalej**.
1. W obszarze **Rejestr i urządzenie** wybierz opcję **SANFRAN-1**.
1. Wybierz **Aktywuj**. Nastąpi wylogowanie i przeniesienia na stronę logowania w punkcie sprzedaży.
1. Teraz możesz zalogować się do środowiska punktu sprzedaży w chmurze przy użyciu identyfikatora operatora **000713** i hasła **123**.

## <a name="set-up-your-site-in-commerce"></a>Konfigurowanie witryny w usłudze Commerce

Aby rozpocząć konfigurowanie witryny oceny w usłudze Commerce, wykonaj następujące kroki.

1. Zaloguj się do konstruktora witryny przy użyciu adresu URL zanotowanego podczas inicjowania usługi handlu elektronicznego w trakcie aprowizacji (zobacz [Inicjowanie usługi handlu elektronicznego](provisioning-guide.md#initialize-e-commerce)).
1. Wybierz witrynę **Fabrikam**, aby otworzyć okno dialogowe konfiguracji witryny.
1. Wybierz domenę, która została wprowadzona podczas inicjowania aplikacji e-Commerce.
1. Wybierz opcję **Rozszerzony sklep online Fabrikam** jako kanał domyślny. (Upewnij się, że wybrano **rozszerzony** sklep internetowy).
1. Wybierz wartość **en-us** jako język domyślny.
1. Pozostaw niezmienioną wartość pola **Ścieżka**.
1. Kliknij przycisk **OK**. Zostanie wyświetlona lista stron w witrynie.
1. Powtórz kroki 2-7 dla witryny **AdventureWorks** (która jest mapowana do kanału **Sklep internetowy AW**) i witryny **AdventureWorks Biznes** (która jest mapowana do kanału **Sklep internetowy AW** Biznes). Jeśli pole **Ścieżka** dla witryny Fabrikam jest puste, należy dodać ścieżki dla tych dwóch witryn AdventureWorks (na przykład „aw” i „awbusiness”).

## <a name="enable-jobs"></a>Włącz zadania

Aby włączyć zadania w aplikacji Commerce, wykonaj następujące kroki.

1. Zaloguj się do środowiska (HQ).
1. Korzystając z menu po lewej stronie, przejdź do pozycji **Retail i Commerce \> Zapytania i raporty \> Zadania wsadowe**.

    Pozostałe kroki tej procedury muszą zostać zakończone dla każdego z następujących zadań:

    * Przetwarzanie powiadomień pocztą e-mail dla zamówienia sieci sprzedaży
    * Dostępność produktu
    * P-0001
    * Zadanie synchronizowania zamówień

1. Użyj szybkiego filtru, aby wyszukać zadanie według nazwy.
1. Jeśli stan zadania to **W trakcie**, wykonaj następujące kroki:

    1. Wybierz rekord.
    1. W okienku akcji na karcie **Zadanie wsadowe** wybierz pozycję **Zmień status**.
    1. Wybierz pozycję **Anuluj**, a następnie kliknij przycisk **OK**.

1. Jeśli stan zadania to **Wstrzymane**, wykonaj następujące kroki:

    1. Wybierz rekord.
    1. W okienku akcji na karcie **Zadanie wsadowe** wybierz pozycję **Zmień status**.
    1. Wybierz pozycję **Oczekiwanie** i kliknij przycisk **OK**.

Opcjonalnie można również określić interwał cyklu równy jednej (1) minucie dla następujących zadań:

* Przetwarzanie zadania powiadomień pocztą e-mail dla zamówienia sieci sprzedaży
* Zadanie P-0001
* Zadanie synchronizowania zamówień

### <a name="run-full-data-synchronization"></a>Uruchamianie pełnej synchronizacji danych

Aby uruchomić pełną synchronizację danych w aplikacji Commerce, wykonaj następujące kroki w Commerce headquarters.

1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Handel detaliczny i inny \> Ustawienia centrali \> Transfer danych w Commerce \> Baza danych kanału**.
1. Wybierz kanał o nazwie **scXXXXXXXXX**.
1. W okienku akcji wybierz **Pełna synchronizacja danych**.
1. Wpisz **9999** jako harmonogram dystrybucji.
1. Kliknij przycisk **OK**.
1. Kliknij przycisk **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Testowanie informacji o karcie kredytowej w celu dokonania zakupów testowych

Aby przeprowadzić transakcje testowe w witrynie, można użyć następujących testowych informacji o karcie kredytowej:

- **Numer karty:** 4111-1111-1111-1111
- **Data ważności:** 10/30
- **Kod wartości weryfikacji karty (CVV):** 737

> [!IMPORTANT]
> Nigdy w żadnym wypadku nie próbuj używać rzeczywistych informacji o karcie kredytowej w witrynie testowej.

## <a name="next-steps"></a>Następne kroki

Po zakończeniu czynności obsługi administracyjnej i konfiguracji można rozpocząć korzystanie ze środowiska oceny. Użyj adresu URL konstruktora witryn Commerce, aby przejść do środowiska tworzenia. Użyj adresu URL witryny Commerce, aby przejść do środowiska witryny klienta platformy handlu detalicznego.

Aby skonfigurować opcjonalne funkcje środowiska oceny usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska oceny usługi Commerce](cpe-optional-features.md).

> [!NOTE]
> Środowiska oceniania handlu są wstępnie załadowane do dzierżawy Azure Active Directory (Azure AD) B2C (business-to-consumer) w celach demonstracyjnych. Konfigurowanie własnej dzierżawy Azure AD B2C nie jest wymagane w przypadku środowisk oceniania. Jeśli jednak środowisko oceniania jest konfigurowane w celu korzystania z własnej dzierżawy Azure AD, należy dodać ``https://login.commerce.dynamics.com/_msdyn365/authresp`` jako adres URL odpowiedzi w aplikacji Azure AD B2C za pośrednictwem Azure Portal.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="site-builder-channel-list-is-empty-when-configuring-site"></a>Lista kanałów konstruktora witryn jest pusta podczas konfigurowania witryny

Jeśli kreator witryn nie wyświetla żadnych kanałów sklepu internetowego, w centrali upewnij się, że kanały zostały dodane do Commerce Scale Unit, jak opisano w sekcji [Zanim zaczniesz](#before-you-start) powyżej. Uruchom też **Zainicjuj harmonogram handlu** z wartością **Usuń istniejącą konfigurację** ustawioną na **Tak**.  Po wykonaniu tych kroków na stronie **Baza danych kanału** (**Sprzedaż detaliczna i handel \> Konfiguracja centrali \> Harmonogram handlu \> Baza danych kanałów**) uruchom zadanie **9999** na Commerce Scale Unit.

### <a name="color-swatches-are-not-rendering-on-the-category-page-but-are-rendering-on-the-product-details-page-pdp-page"></a>Zmiany koloru nie są renderowaniem na stronie kategorii, lecz są renderowaniem na stronie szczegółów produktu (PDP)

Aby zapewnić, że kolory i rozmiary można ulepszać, należy wykonać następujące kroki.

1. W centrali wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Kategorie kanału sprzedaży i atrybuty produktów**.
1. W lewym okienku wybierz kanał sklepu internetowego, a następnie **Ustaw metadane atrybutu**.
1. Ustaw w opcji **Pokaż atrybut kanału** wartość **Tak**, ustaw opcję **Może być wyszukany** na **wartość Tak**, a następnie wybierz opcję **Zapisz**. 
1. Wróć na stronę kanału sklepu internetowego, a następnie wybierz pozycję **Publikowanie aktualizacji kanału**.
1. Przejdź do **Sprzedaż detaliczna i handel \> Konfiguracja centrali \> Harmonogram handlu \> Baza danych kanałów** i uruchom zadanie **9999** w module Commerce Scale Unit.

### <a name="business-features-dont-appear-to-be-turned-on-for-the-adventureworks-business-site"></a>Funkcje biznesowe nie są wyświetlane jako włączone dla witryny AdventureWorks biznesowej

W centrali upewnij się, że kanał sklepu internetowego jest skonfigurowany z **Typem klienta** ustawionym na **B2B**. Jeśli **typem klienta** jest **B2C**, należy utworzyć nowy kanał, ponieważ nie można edytować istniejącego kanału. 

Dane demonstracyjne dostarczone w wersji Commerce 10.0.26 i wcześniejszych zawierały błąd, który powodował, że kanał **Biznes AW online** był nieprawidłowo skonfigurowany. Rozwiązaniem jest utworzenie nowego kanału z tymi samymi ustawieniami i konfiguracjami z wyjątkiem **Typ klienta**, który powinien być ustawiony na **B2B**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie środowiska oceny usługi Dynamics 365 Commerce](cpe-overview.md)

[Ustanowienie środowiska oceny Dynamics 365 Commerce](provisioning-guide.md)

[Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce](cpe-optional-features.md)

[Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce](cpe-bopis.md)

[Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Konfigurowanie dzierżawy B2C w module Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
