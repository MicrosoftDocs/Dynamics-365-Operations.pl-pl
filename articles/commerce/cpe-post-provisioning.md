---
title: Konfiguruj środowisko piaskownicy usługi Dynamics 365 Commerce
description: W tym artykule opisano sposób konfigurowania środowiska piaskownicy aplikacji Microsoft Dynamics 365 Commerce po jego inicjacji.
author: psimolin
ms.date: 06/14/2022
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
ms.openlocfilehash: 259a580981003f135e234f66e9e93ceb18605412
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013116"
---
# <a name="configure-a-dynamics-365-commerce-sandbox-environment"></a>Konfiguruj środowisko piaskownicy usługi Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób konfigurowania środowiska piaskownicy aplikacji Microsoft Dynamics 365 Commerce po jego inicjacji.

Procedury opisane w tym artykule należy wykonać dopiero po zakończeniu aprowizacji środowiska piaskownicy usługi Commerce. Aby uzyskać informacje dotyczące sposobu aprowizowania środowiska piaskownicy usługi Commerce, zobacz [Aprowizowanie środowiska piaskownicy usługi Commerce](provisioning-guide.md).

Po zakończeniu kompleksowej aprowizacji środowiska piaskownicy usługi Commerce wykonać dodatkowe czynności konfiguracyjne po aprowizacji, aby można było rozpocząć używanie środowiska. Aby wykonać te kroki, należy użyć usług Microsoft Dynamics Lifecycle Services (LCS) i Dynamics 365 Commerce.

## <a name="before-you-start"></a>Przed rozpoczęciem

1. Zaloguj się do [portalu usługi LCS](https://lcs.dynamics.com).
1. Przejdź do projektu.
1. Wybierz swoje środowisko na liście.
1. W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do środowiska**. Nastąpi wysłanie do modułu Commerce Headquarter.
1. Upewnij się, że wybrano firmę **USRT** w prawym górnym rogu. Ta osoba prawna została wstępnie skonfigurowana w danych demonstracyjnych.
1. Przejdź do pozycji **Parametry Commerce \> Konfigurowanie parametrów** i upewnij się, że istnieje wpis **ProductSearch.UseAzureSearch** ustawiony na **true**. Jeśli ten wpis nie istnieje, dodaj go i ustaw wartość **prawda**.
1. Przejdź do **Handel detaliczny i inny \> Ustawienia Headquarters \> Harmonogram handlu \> Zainicjuj harmonogram handlu**. W menu **Inicjowanie harmonogramu handlu** upewnij się, że opcja **Usuń istniejącą konfigurację** jest ustawiona na wartość **Tak**, a następnie kliknij przycisk **OK**.
1. Aby kanały sklepu i handlu elektronicznego działały poprawnie, należy je dodać do Commerce Scale Unit. Przejdź do **Retail i Commerce \> Konfiguracja centrali \> Harmonogram handlu \> Baza danych kanałów**, a następnie w panelu po lewej stronie wybierz Commerce Scale Unit. Na skróconej karcie **kanału sprzedaży** detalicznej dodaj **sklep internetowy AW**, **sklep internetowy AW Business** i rozszerzone kanały **sklepu internetowego firmy Fabrikam**, jeśli planujesz korzystanie z tych kanałów handlu elektronicznego. Opcjonalnie można dodać sklepy sieci sprzedaży, jeśli będzie korzystać z punktu sprzedaży (POS) (na przykład **Seattle**, **San Francisco** i/lub **San Jose**).
1. Aby zapewnić synchronizację wszystkich zmian z bazą danych kanału, wybierz opcję **Baza danych kanału \> Pełna synchronizacja danych** dla Commerce Scale Unit.

Podczas wykonywania działań związanych z inicjowaniem obsługi administracyjnej w module Commerce Headquarter należy się upewnić, że firma **USRT** jest zawsze zaznaczona.

## <a name="configure-the-point-of-sale"></a>Konfigurowanie punktu sprzedaży

### <a name="associate-a-worker-with-your-identity"></a>Kojarzenie pracownika z Twoją tożsamością

Aby skojarzyć pracownika z tożsamością, wykonaj następujące kroki w Commerce Headquarters.

1. Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Pracownicy etatowi \> Pracownicy**.
1. Na liście znajdź i wybierz następujący rekord: **000713 - Andrew Collette**. Ten przykład użytkownik jest skojarzony ze sklepem San Francisco, który będzie używany w następnej sekcji.
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

## <a name="set-up-your-e-commerce-sites"></a>Konfigurowanie witryn handlu elektronicznego

Dostępne są trzy witryny demonstracyjne handlu elektronicznego: Fabrikam, Adventure Works i Adventure Works Business. Aby skonfigurować każdą witrynę demonstracyjną, należy wykonać poniższe kroki.

1. Zaloguj się do konstruktora witryny przy użyciu adresu URL zanotowanego podczas inicjowania usługi handlu elektronicznego w trakcie aprowizacji (zobacz [Inicjowanie usługi handlu elektronicznego](provisioning-guide.md#initialize-e-commerce)).
1. Wybierz witrynę (**Fabrikam**, **Adventure Works** lub **Adventure Works Business**), aby otworzyć okno dialogowe konfiguracji witryny.
1. Wybierz domenę, która została wprowadzona podczas inicjowania usługi Commerce.
1. W centrali wybierz wstępnie skonfigurowany kanał sklepu internetowego (**Rozszerzony sklep internetowy Fabrikam**, **Sklep internetowy AW** lub **Sklep internetowy AW Business**), który odpowiada kanałowi domyślnemu.
1. Wybierz wartość **en-us** jako język domyślny.
1. Skonfiguruj pola ścieżki. Pole to można pozostawić puste dla jednej witryny, ale w przypadku używania tej samej nazwy domeny dla wielu witryn konieczne będzie skonfigurowanie tej samej nazwy domeny. Na przykład, jeśli nazwą domeny jest `https://www.constoso.com`, można użyć pustej ścieżki dla Fabrikam (`https://contoso.com`), a następnie użyć „aw” dla Adventure Works (`https://contoso.com/aw`) i „awbusiness” dla witryny biznesowej Adventure Works (`https://contoso.com/awbusiness`).
1. Kliknij przycisk **OK**. Zostanie wyświetlona lista stron w witrynie.
1. Opcjonalnie powtórz kroki 2–7, aby skonfigurować w razie potrzeby inne witryny demonstracyjne.

## <a name="enable-jobs"></a>Włącz zadania

Aby włączyć zadania w aplikacji Commerce, wykonaj następujące kroki.

1. Zaloguj się do środowiska centrali.
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

Po zakończeniu czynności obsługi administracyjnej i konfiguracji można rozpocząć korzystanie ze środowiska piaskownicy. Użyj adresu URL konstruktora witryn Commerce, aby przejść do środowiska tworzenia. Użyj adresu URL witryny Commerce, aby przejść do środowiska witryny klienta platformy handlu detalicznego.

Aby skonfigurować opcjonalne funkcje środowiska piaskownicy usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska piaskownicy usługi Commerce](cpe-optional-features.md).

Aby umożliwić użytkownikom handlu elektronicznego logowanie się do witryny handlu elektronicznego, wymagana jest dodatkowa konfiguracja, aby można było włączyć uwierzytelnianie witryny przez klienta biznesowego (B2C) Azure Active Directory. Instrukcje znajdziesz w [Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-b2c-tenant.md).

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

[Ustanowienie środowiska piaskownicy usługi Dynamics 365 Commerce](provisioning-guide.md)

[Konfiguruj funkcje opcjonalne środowiska piaskownicy usługi Dynamics 365 Commerce](cpe-optional-features.md)

[Konfigurowanie BOPIS w środowisku piaskownicy Dynamics 365 Commerce](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Konfigurowanie dzierżawy B2C w module Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
