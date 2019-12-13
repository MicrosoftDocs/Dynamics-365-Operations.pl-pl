---
title: Konfigurowanie środowiska oceny handlu elektronicznego
description: Ten podręcznik zawiera instrukcje krok po kroku dotyczące obsługi i konfigurowania środowiska Microsoft Dynamics 365 Commerce w wersji zapoznawczej.
author: v-chgri
manager: annbe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0dce2796e69cd8dee87cba176a521c26c81eb1a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771687"
---
# <a name="configure-an-e-commerce-evaluation-environment"></a>Konfigurowanie środowiska oceny handlu elektronicznego

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ten podręcznik zawiera instrukcje krok po kroku dotyczące obsługi i konfigurowania środowiska Microsoft Dynamics 365 Commerce w wersji zapoznawczej. Przed rozpoczęciem zaleca się, aby co najmniej przejrzeć dokumentację w celu uzyskania ogólnego pojęcia co zawiera proces i przewodnik.

*Uwaga: Jeśli nie przyznano jeszcze dostępu do podglądu rozwiązania Microsoft Dynamics 365 Commerce, możesz zażądać dostępu do podglądu z [witryny sieci Web Commerce](https://aka.ms/Dynamics365CommerceWebsite).*

## <a name="summary"></a>Sumarycznie
Aby zapewnić pomyślne zainicjowanie obsługi środowiska, projekt musi zostać utworzony z określoną nazwą i typem produktu. Środowisko i Retail Cloud Scale Unit mają także określone parametry, które należy wykonać w celu późniejszego rozpoczęcia tworzenia prowizji w e-Commerce. Instrukcje zawarte w tym podręczniku zawierają wszystkie wymagane kroki, które należy wykonać, i parametry, które należy zastosować.

Po pomyślnym zainicjowaniu obsługi administracyjnej istnieje kilka kroków, które należy wykonać, aby przygotować środowisko podglądu. Niektóre kroki są opcjonalne, w zależności od tego, jakie aspekty systemu mają być oceniane. Aby później zmienić zdanie, zawsze możesz wykonać kroki opcjonalne później.

Jeśli masz pytania dotyczące czynności związanych z zastrzeganiem lub występują jakieś problemy, poinformuj nas na [grupie Microsoft Dynamics 365 Commerce Podgląd Yammer](https://aka.ms/Dynamics365CommercePreviewYammer). 

## <a name="prerequisites"></a>Wymagania wstępne
Poniżej przedstawiono wymagania wstępne dotyczące obsługi środowiska wersji Dynamics 365 podgląd:
* Masz dostęp do **portalu Lifecycle Services (usługi LCS)**
* Użytkownik został **zaakceptowany do podglądu programu Dynamics 365 Commerce**
* Użytkownik ma uprawnienia wymagane do tworzenia projektu dla **Potencjalne przedsprzedaże** lub **Wykonaj migrację, twórz rozwiązania i poznaj rozwiązanie**
* Użytkownik jest członkiem roli **Menedżer środowiska** lub **Właściciela projektu** w projekcie, w którym będzie inicjowana obsługa środowiska
* Masz uprawnienia administratora do subskrypcji Azure lub skontaktuj się z administratorem subskrypcji, który może wykonać dwa kroki wymagające uprawnień administratora w Twoim imieniu
* Twój **identyfikator dzierżawy usługi AAD** jest dostępny
* Utworzono **grupę zabezpieczeń AAD**, która ma być używana jako **Grupa Administratorzy systemu w e-Commerce** i jest dostępny jej identyfikator
* Utworzono **grupę zabezpieczeń AAD**, która ma być używana jako **Grupa moderatora klasyfikacji i przeglądów**, a użytkownik ma dostęp do jej identyfikatora (może to być ten sam element SG, co systemowa grupa administratorów powyżej)
## <a name="provisioning-preview-environment"></a>Środowisko podglądu przypisywania zasobów
Instrukcje te obejmują zainicjowanie obsługi środowiska podglądu Microsoft Dynamics 365 Commerce. Po pomyślnym wykonaniu tych kroków zostanie utworzone środowisko podglądu, które jest gotowe do skonfigurowania. Wszystkie opisane działania są wykonywane w portalu usługi LCS.

*Zauważ, że dostęp w wersji podglądu jest powiązany z kontem usługi LCS i organizacją określoną w aplikacji podglądu. Aby zainicjować obsługę administracyjną, musisz skorzystać z tego samego konta Jeśli konieczne jest użycie różnych kont usługi LCS lub dzierżawy dla środowiska w wersji podglądu, trzeba podać te szczegóły. Aby uzyskać informacje o kontakcie, zobacz temat „dodatkowe zasoby” poniżej.*
### <a name="before-starting"></a>Przed rozpoczęciem
##### <a name="grant-access-to-e-commerce-applications"></a>Udzielanie dostępu do aplikacji e-Commerce

*Uwaga: **osoba rejestrująca musi być administratorem dzierżawy usługi AAD**. Jeśli ten krok nie zostanie zakończony, pozostała część kroków inicjowania obsługi nie powiedzie się.*

1. W tym kroku potrzebujesz **identyfikatora dzierżawy w usłudze AAD**. Aby uzyskać dostęp do Twojej subskrypcji Azure, musisz autoryzować aplikacje e-Commerce Najprostszym sposobem osiągnięcia tego celu jest zgromadzenie adresu URL w następujący sposób:

https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345

2. **Nie należy bezpośrednio klikać adresu URL**, a następnie kopiować go i wklejać do przeglądarki lub edytora tekstów i zamienić **\{AAD_TENANT_ID\}** z **Identyfikatorem dzierżawy AAD** przed przechodzeniem do adresu URL.
3. Zostanie wyświetlone okno dialogowe logowania do usługi Microsoft AAD, w którym można potwierdzić, że użytkownik chce udzielić „Dynamics 365 Commerce (Podgląd)” dostępu do Twojej subskrypcji.
4. Nastąpi wysłanie do strony, która potwierdza, że operacja zakończyła się pomyślnie.

##### <a name="log-in-to-the-lcs"></a>Zaloguj się w kasie LCS
1. Zaloguj się w portalu LCS: https://lcs.dynamics.com
1. Upewnij się, że zalogowano się przy użyciu tego samego konta usługi LCS, które zostało użyte do zażądania dostępu do podglądu.
##### <a name="confirm-that-preview-features-are-available-and-enabled"></a>Potwierdź, że funkcje wersji podglądu są dostępne i włączone
1. Na stronie głównej usługi LCS przewiń do prawej strony i kliknij pozycję **Podgląd funkcji podglądu**.
1. Przewiń w dół do „prywatnej funkcji podglądu” i upewnij się, że są dostępne i włączone następujące funkcje:
    1. **Ocena e-Commerce**
    1. **Środowiska podglądu programu Commerce**
1. Jeśli nie widzisz tych funkcji na liście, skontaktuj się z nami za pomocą poczty e-mail, konta usługi LCS i szczegółów dzierżawy. Aby uzyskać informacje o sposobach kontaktowania się z nami, zobacz **dodatkowe zasoby**.

![Kafelek podglądu zarządzania](./media/preview1.png)

![Funkcje w wersji zapoznawczej](./media/preview2.png)
### <a name="create-project"></a>Utwórz projekt
##### <a name="creating-new-project"></a>Tworzenie nowego projektu
1. Kliknij **+**, aby utworzyć nowy projekt.
1. Jeśli jesteś partnerem, wybierz opcję **Wykonaj migrację, twórz rozwiązania i poznaj rozwiązanie**.
1. Jeśli jesteś odbiorcą, wybierz **Potencjalne przedsprzedaże**.
1. Wprowadź odpowiednio nazwę, opis i branżę.
1. W polu **Nazwa produktu** wybierz opcję **Dynamics 365 Retail**.
1. W polu **Wersja produktu** wybierz opcję **Dynamics 365 Retail**.
1. W przypadku **metodologii** wybierz **Dynamics Retail metodologia implementacji**.
1. W razie potrzeby można zaimportować role i użytkowników z istniejącego projektu.
1. Kliknij **Utwórz**.
1. Użytkownik jest wysyłany do widoku projektu.
##### <a name="add-azure-connector"></a>Dodaj łącznik Azure
1. Jeśli jesteś partnerem, kliknij opcję **ustawienia projektu** na kafelkach narzędzia po prawej stronie.
1. Jeśli jesteś odbiorcą, wybierz z górnego menu **Ustawienia projektu**.
1. Wybierz **łączniki Azure**.
1. Kliknij **+ Dodaj**, aby dodać łącznik Azure.
1. Należy wprowadzić nazwę.
1. Wpisz **Identyfikator subskrypcji Azure**.
1. Włączanie **Konfiguruj do użycia usługi Azure Resource Manager (ARM)**.
1. Sprawdź, czy **domena dzierżawy usługi AAD w usłudze Azure (lub identyfikator)** jest poprawna. W razie potrzeby skonsultuj się z administratorem subskrypcji Azure.
1. Kliknij przycisk **Dalej**.
1. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby udzielić wymaganych aplikacji dostępu do Twojej subskrypcji. W razie potrzeby skonsultuj się z administratorem subskrypcji Azure:
    1. Zaloguj się w portalu Azure: https://portal.azure.com/
    1. Upewnij się, że wybrano poprawny katalog.
    1. Kliknij opcję **subskrypcje** w menu po lewej stronie.
    1. Zlokalizuj poprawną subskrypcję z listy i wybierz ją. W razie potrzeby należy skorzystać z funkcji wyszukiwania.
    1. Wybierz opcję **Kontrola dostępu (IAM)** z menu.
    1. Kliknij przycisk **Dodaj** w obszarze **Dodaj przypisanie roli** po prawej stronie. Zostanie otwarte okienko **Dodawanie przypisania roli**.
    1. W polu **rola** wybierz opcję **Współautor**.
    1. Aby **Uzyskać dostęp do systemu**, należy go pozostawić jako **użytkownika Azure AD, grupę lub nazwę główną usługi**.
    1. W obszarze **Wybierz** wprowadź wartość **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.
    1. Wybierz z listy opcję **Usługi wdrażania Dynamics [wsfed-enabled]**.
    1. Kliknij przycisk **Zapisz**.
1. Kliknij przycisk **Dalej**.
1. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby udzielić wymaganych aplikacji dostępu do Twojej subskrypcji. W razie potrzeby skonsultuj się z administratorem subskrypcji Azure.
1. Kliknij przycisk **Dalej**.
1. W przypadku **regionu platformy Azure** wybierz **Wschodnie stany USA**, **Wschodnie stany USA 2**, **Zachodnie stany USA** lub **Zachodnie stany USA 2**.
1. Kliknij przycisk **Połącz**.
1. Program łącznik Azure powinien pojawić się na liście.
### <a name="import-extension"></a>Rozszerzenie importu
1. Przejdź wstecz do strony głównej projektu, klikając nazwę projektu na górze.
1. Jeśli jesteś partnerem, kliknij opcję **Biblioteka elementów zawartości** na kafelkach narzędzia po prawej stronie.
1. Jeśli jesteś odbiorcą, wybierz z górnego menu **Biblioteka elementów zawartości**.
1. Wybierz **Wdrażalny pakiet oprogramowania** z listy po lewej stronie.
1. W okienku akcji kliknij pozycję **IMPORTUJ**.
1. Wybierz **rozszerzenie podstawowe demonstracji podgladu Commerce** z listy składników majątku w **BIBLIOTEKA UDOSTĘPNIONYCH ELEMENTÓW ZAWARTOŚCI**.
1. Kliknij przycisk **Pobierz**.
1. Zostanie ona zwrócona do biblioteki składników majątku, a rozszerzenie ma zostać wyświetlone na liście.

![Tworzenie projektu - wersje](./media/import.png)
### <a name="deploy-environment"></a>Wdróż środowisko

*Uwaga: istnieje możliwość, że kroki 6, 7 i/lub 8 nie będą wyświetlane, ponieważ ekrany z pojedynczą opcją zostaną pominięte. W widoku **Parametry środowiska** sprawdź, czy masz tekst „Dynamics 365 Commerce (wersja zapoznawcza) — Demonstracja (10.0.6 z aktualizacją platformy 30)” bezpośrednio powyżej pola **Nazwa środowiska**. Poniżej znajduje się zrzut ekranu.*

1. Z menu górnego wybierz opcję **Środowiska obsługiwane w chmurze**.
1. Kliknij przycisk **+ Dodaj**, aby dodać środowisko.
1. Dla **Wersji aplikacji**, wybierz **10.0.6**.
1. W przypadku **Wersji platformy** wybierz **Aktualizację platformy 30**.
1. Kliknij przycisk **Dalej**.
1. W obszarze topologia środowiska wybierz opcję **DEMO**.
1. W obszarze topologia środowiskowa wybierz opcję **Dynamics 365 Commerce (Podgląd) — Demo**.
1. Jeśli wcześniej skonfigurowano jeden łącznik Azure, zostanie on użyty dla tego środowiska. W przypadku skonfigurowania wielu łączników Azure można wybrać opcję wyboru łącznika, który ma być używany: **Wschodnie stany USA**, **Wschodnie stany USA 2**, **Zachodnie stany USA** lub **Zachodnie stany USA 2** (zalecane w celu zapewnienia optymalnej wydajności na zakończenie)
1. Wprowadź **Nazwę środowiska**.
1. Dostosuj rozmiar maszyny wirtualnej w takiej postaci, w jakiej jest dopasowana. (Zalecamy użycie maszyny wirtualnej SKU **D13 v2**.)
1. W takim przypadku należy pozostawić **Ustawienia zaawansowane**.
1. Po przejrzeniu warunków cenowych i licencyjnych na ekranie zaznacz pole, aby wskazać umowę.
1. Kliknij przycisk **Dalej**.
1. Po sprawdzeniu, że szczegóły są poprawne, na ekranie potwierdzenia wdrożenia kliknij przycisk **Wdróż**.
1. Powrócisz do widoku **Środowiska hostowane w chmurze** i Twoje środowisko powinno pojawić się na liście.
1. Żądane środowisko będzie widoczne jako kolejkowane, a następnie wdrożone. Ukończenie wszystkich przepływów pracy środowiska zajmie trochę czasu, dlatego należy sprawdzić z powrotem za kilka godzin (około 6 – 9 godzin).
1. Przed kontynuowaniem upewnij się, że stan środowiska jest **Wdrożony**.

![Tworzenie projektu - wersje](./media/project1.png)

![Tworzenie projektu - topologia 1](./media/project2.png)

![Tworzenie projektu - topologia 2](./media/project3.png)

![Tworzenie projektu — parametry środowiska](./media/project4.png)
### <a name="initialize-rcsu"></a>Zainicjuj RCSU
1. W widoku **Środowiska hostowane w chmurze** wybierz środowisko z listy.
1. W widoku środowisko po prawej stronie ekranu kliknij opcję **Pełne szczegóły**. Zostanie wyświetlony widok szczegóły środowiska.
1. W obszarze **FUNKCJE ŚRODOWISKA** kliknij opcję **Zarządzaj**.
1. Na karcie **Retail** kliknij opcję **Inicjuj**. Zostanie wyświetlony widok parametrów inicjacji RCSU.
1. W przypadku **REGION** wybierz **Wschodnie stany USA**, **Wschodnie stany USA 2**, **Zachodnie stany USA** lub **Zachodnie stany USA 2**.
1. W przypadku **WERSJI** należy najpierw wybrać opcję **Określ wersję** z listy rozwijanej, a następnie w polu tekstowym wyświetlonym poniżej określić **9.16.19262.5**. *Uwaga: należy **określić dokładną wersję** wymienioną tutaj, aby uniknąć konieczności późniejszej aktualizacji RCSU w celu poprawienia wersji.*
1. Włącz **Zastosuj rozszerzenie**.
1. Z listy rozszerzeń wybierz **podstawowe rozszerzenie demo podglądu Commerce**.
1. Kliknij **Inicjuj**.
1. Po sprawdzeniu, że szczegóły są poprawne, na ekranie potwierdzenia wdrożenia kliknij przycisk **Tak**.
1. Powrót do widoku **Zarządzanie Retail** jest uaktywniany z użyciem karty **Retail**. RCSU zostało dodane do kolejki w celu zainicjowania obsługi administracyjnej.
1. Poczekaj, aż stan RCSU jest **UDANE**, zanim zaczniesz kontynuować (zajmie około 2-5 godzin).
### <a name="initialize-e-commerce"></a>Inicjalizowanie e-Commerce
1. Przełącz się na **kartę e-Commerce (Podgląd)**.
1. Po przejrzeniu zgody użytkownika kliknij przycisk **Ustawienia**.
1. Wprowadź nazwę dla **nazwy dzierżawy e-Commerce**. Należy jednak pamiętać, że będzie ono widoczne w niektórych adresach URL wskazujących na to wystąpienie w e-Commerce.
1. W polu **Nazwa Retail cloud scale unit** wybierz RCSU z listy (lista powinna mieć tylko jedną opcję).
1. **Geografia e-Commerce** jest automatycznie wypełniana i nie można jej zmienić.
1. Kliknij przycisk **Dalej**, aby kontynuować.
1. W przypadku **obsługiwanych nazw hostów** wprowadź prawidłową domenę (np. www.fabrikam.com).
1. W przypadku **grupy zabezpieczeń AAD dla administratora systemu** wprowadź identyfikator AAD SG, który ma być używany jako grupa administratora ssystemu e-Commerce.
1. W przypadku **grupy zabezpieczeń AAD w przypadku klasyfikacji i moderatora przeglądu** wprowadź identyfikator AAD SG ID, który ma być używany jako Klasyfikacja i Grupa moderatora recenzji.
1. Pozostaw puste wartości **B2C** (7 pól rozpoczynających się od B2C).
1. Opuść **włączenie usługi klasyfikacji i przeglądu**.
1. Kliknij **Inicjuj**.
1. Powrót do widoku **Zarządzanie Retail** jest uaktywniany z użyciem karty **e-Commerce (podgląd)**. Inicjowanie usługi e-Commerce zostało rozpoczęte.
1. Przed kontynuowaniem poczekaj na **INICJALIZOWANIE POWIODŁO SIĘ** stanu inicjowania e-Commerce.
1. W obszarze **ŁĄCZA** w prawym dolnym rogu.
    * Zanotuj łącze do **witryny e-Commerce**. To jest łącze do katalogu głównego witryny C2.
    * Zanotuj łącze do **narzędzia zarządzania witryny e-Commerce**. Jest to łącze do narzędzia do zarządzania witryną (narzędzie do tworzenia oddziału C1).
## <a name="post-provisioning-steps"></a>Kroki po zainicjowaniu obsługi
Na tym etapie środowisko zostało zainicjowane jako kompleksowe rozwiązanie, ale nadal istnieją kroki konfiguracyjne, które należy zachować przed rozpoczęciem oceny środowiska.
### <a name="before-starting"></a>Przed rozpoczęciem
1. Z menu górnego wybierz opcję **Środowiska obsługiwane w chmurze**.
1. Wybierz swoje środowisko z listy.
1. Kliknij opcję **Pełne szczegóły** z informacji o środowisku po prawej stronie.
1. Kliknij przycisk **Zaloguj**, aby otworzyć menu, wybierz opcję **Zaloguj do środowiska**.

Upewnij się, że wybrano **USRT** firmę (prawy górny róg)

### <a name="configure-pos"></a>Konfiguruj usługę POS
##### <a name="associate-worker-with-your-identity"></a>Skojarz pracownika z Twoją tożsamością
1. Korzystając z menu po lewej stronie, przejdź do **Modułu > Retail > Pracownicy etatowi > Pracownicy**.
1. Na liście znajdź i zaznacz odpowiedni rekord **000713 - Andrew Collette**.
1. W okienku akcji kliknij pozycję **Retail**.
1. Kliknij **Skojarz istniejącą tożsamość**.
1. W polu **adres e-mail** (na prawo od **wyszukiwania za pomocą poczty e-mail**) wpisz swój adres e-mail.
1. Kliknij przycisk **Wyszukaj**.
1. Wybierz rekord z nazwą użytkownika.
1. Kliknij przycisk **OK**.
1. Kliknij przycisk **Zapisz**.
##### <a name="activate-cloud-pos"></a>Aktywować punkt sprzedaży w chmurze
1. Zaloguj się w portalu LCS.
1. Przejdź do projektu.
1. Z menu górnego wybierz opcję **Środowiska obsługiwane w chmurze**.
1. Wybierz swoje środowisko z listy.
1. Kliknij opcję **Pełne szczegóły** z informacji o środowisku po prawej stronie.
1. Kliknij przycisk **Zaloguj**, aby otworzyć menu, wybierz opcję **Zaloguj do punktu sprzedaży w chmurze**, należy załadować punkt sprzedaży.
1. Kliknij przycisk **Dalej**.
1. Zaloguj się, aby połączyć swoje konto ADD.
1. W polu **Nazwa sklepu** wybierz opcję **San Francisco**.
1. Kliknij przycisk **Dalej**.
1. W obszarze **Rejestr i urządzenia** wybierz opcję **SANFRAN-1**.
1. Kliknij **Aktywacja**.
1. Należy wylogować się i zakończyć na ekranie logowania do punktu sprzedaży.
1. Teraz możesz zalogować się do środowiska punktu sprzedaży w chmurze przy użyciu identyfikatora operatora **000713** i hasła **123**.
### <a name="site-setup"></a>Ustawienia witryny
1. Zaloguj się do **narzędzia zarządzania oddziałem**, używając wcześniej zanotowanego adresu URL.
1. Kliknij łącze w witrynie **Fabrikam**, aby otworzyć okno dialogowe konfiguracji witryny.
1. W przypadku domeny wybierz domenę, która została wprowadzona wcześniej podczas inicjowania e-Commerce.
1. W przypadku kanału domyślnego wybierz opcję **Rozszerzony sklep online Fabrikam**. *Uwaga: Upewnij się, że wybrano **rozszerzony** sklep internetowy*
1. W przypadku języka domyślnego wybierz wartość **EN-US**.
1. Pozostaw **Ścieżkę** w takiej postaci.
1. Kliknij przycisk **OK**.
1. Użytkownik zostanie wysłany do listy stron w witrynie.
### <a name="enable-jobs"></a>Włącz zadania
1. Zaloguj się do środowiska (HQ)
1. Korzystając z menu po lewej stronie, przejdź do **Retail > Zapytania i raporty > Zadania wsadowe**.
1. Wykonaj następujące kroki dla każdej pracy z listy poniżej:
    * **Przetwarzanie powiadomień pocztą e-mail dla zamówienia sieci sprzedaży**.
    * **Dostępność produktu**.
    * **P-0001**.
    * **Zadanie synchronizowania zamówień**.
1. Aby wyszukać zadanie za pomocą jego nazwy (wymienione powyżej), należy użyć szybkiego filtru.
1. Jeśli stan zadania jest **wstrzymany**, należy wykonać następujące kroki:
    1. Wybierz rekord.
    1. W okienku akcji otwórz okno **zadania wsadowe** i kliknij przycisk **Zmień stan**.
    1. Wybierz opcję **Oczekujące** i kliknij przycisk **OK**.
### <a name="run-full-data-sync"></a>Uruchamianie pełnej synchronizacji danych
1. Korzystając z menu po lewej stronie, przejdź do **Moduły > Retail > Ustawienia centrali  > Transfer danych w sieci sprzedaży > Baza danych kanału**.
1. **Domyślny** kanał jest wybierany z listy po lewej stronie. *Wybierz inny dostępny kanał (o nazwie **scXXXXXXXXX**)*.
1. Kliknij opcję **Pełna synchronizacja danych** w okienku akcji.
1. Wpisz **9999** jako harmonogram dystrybucji.
1. Kliknij przycisk **OK**.
1. Kliknij przycisk **OK**.
### <a name="after-these-steps-you-are-ready-to-start-evaluating-your-preview-environment"></a>Po wykonaniu tych kroków można rozpocząć ocenianie środowiska podglądu!
Za pomocą adresu URL **Narzędzia do zarządzania witryną e-Commerce** przejdź do środowiska autorskiego C1 i użyj adresu URL **witryny e-Commerce**, aby przejść do doświadczenia w witrynie C2.

## <a name="additional-resources"></a>Dodatkowe zasoby
### <a name="how-to-find-your-aad-tenant-id"></a>Jak znaleźć identyfikator dzierżawy w usłudze AAD
Identyfikator dzierżawy AAD jest identyfikatorem GUID i wygląda podobnie do tego przykładu: **72f988bf-86f1-41af-91ab-2d7cd011db47**
##### <a name="from-azure-portal"></a>Z portalu Azure
1. Zaloguj się w portalu Azure: https://portal.azure.com/
1. Upewnij się, że wybrano poprawny katalog.
1. Kliknij opcję **Azure Active Directory** w menu po lewej stronie.
1. Wybierz **Właściwości** w obszarze **Zarządzanie**.
1. Identyfikator dzierżawy AAD jest wyświetlany w obszarze **Identyfikator katalogu**.
##### <a name="from-openid-connect-metadata"></a>Z metadanych OpenID Connect
Utwórz **adres URL OpenID**, zastępując **\{TWOJĄ_DOMENĘ\}** swoją domeną, np. microsoft.com: https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration zostanie zmienione na https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration

1. Przejdź do **adresu URL OpenID** z Twoją domeną.
1. Identyfikator dzierżawy AAD może być wyświetlany w wielu wartościach właściwości.
1. Zlokalizuj **authorization_endpoint** i wyodrębnij identyfikator GUID bezpośrednio po **login.microsoftonline.com/**.
### <a name="how-to-find-the-id-of-your-aad-security-group"></a>Zawiera informacje dotyczące wyszukiwania identyfikatora grupy zabezpieczeń usługi AAD
Identyfikator grupy zabezpieczeń usługi AAD jest identyfikatorem GUID i wygląda podobnie do tego przykładu: **436ea7f5-ee6c-40c1-9f08-825c5811066a**

W tym kroku założono, że użytkownik jest członkiem grupy, której identyfikator próbuje zlokalizować.
1. Przejdź do eksploratora wykresów Graph: https://developer.microsoft.com/en-us/graph/graph-explorer#
1. Kliknij **Zaloguj się za pomocą konta Microsoft** i zaloguj się przy użyciu swoich poświadczeń.
1. Po zalogowaniu się kliknij przycisk **Wyświetl więcej próbek** po lewej stronie.
1. Włącz **grupy** z prawego okienka.
1. Zamknij prawe okienko.
1. Kliknij opcję **wszystkie grupy, do których należę**.
1. Zlokalizuj grupę w polu tekstowym **Podgląd odpowiedzi**.
1. Identyfikator grupy zabezpieczeń został zapisany w polu **identyfikator** właściwości.
### <a name="test-credit-card-information-to-perform-test-purchases"></a>Testowanie informacji o karcie kredytowej w celu przeprowadzenia testu zakupów
Aby przeprowadzić transakcje testowe w oddziale, można użyć następujących testów informacji o karcie kredytowej:

Numer karty: 4111-1111-1111-1111, Data wygaśnięcia: 10/20, numer CVV: 737

*Uwaga: w żadnym wypadku nie należy próbować używać rzeczywistych informacji o karcie kredytowej w witrynie testowej!*
### <a name="useful-links"></a>Przydatne łącza
* [LCS (Lifecycle services)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)
* [RCSU (Retail Cloud Scale Unit)](https://docs.microsoft.com/en-us/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)
* [Portal Microsoft Azure](https://azure.microsoft.com/en-us/features/azure-portal)
* [Witryna Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
* [Zasoby pomocy dla rozwiązania Dynamics 365 Retail](../retail/index.md)
### <a name="microsoft-dynamics-365-commerce-preview-support"></a>Pomoc techniczna podglądu Microsoft Dynamics 365 Commerce
Jeśli wystąpią problemy podczas wykonywania kroków dotyczących inicjowania obsługi, odwiedź [Podgląd Microsoft Dynamics 365 Commerce grupa Yammer](https://aka.ms/Dynamics365CommercePreviewYammer) w celu uzyskania pomocy. 

Jeśli masz problemy z dostępem do grupy Yammer, możesz również napisać do nas wiadomość e-mail na **Dynamics365Commerce@microsoft.com**. Ten adres e-mail nie jest aktywnie monitorowany, więc można oczekiwać opóźnienia w odpowiedzi.
***
## <a name="prerequisites-for-optional-features"></a>Wymagania wstępne dotyczące funkcji opcjonalnych
Jeśli chcesz ocenić funkcje transakcyjnej poczty e-mail, muszą być spełnione następujące wymagania wstępne:
* Jest dostępny serwer poczty e-mail (serwer SMTP), który może być używany z poziomu subskrypcji Azure, w której jest inicjowane środowisko wersji zapoznawczej.
* Masz dostęp do nazwy FQDN/IP serwera, numeru portu SMTP oraz szczegółów uwierzytelniania.

Aby ocenić funkcje Digital Asset Management, w szczególnościspożycie nowych obrazów wielokanałowych, należy spełnić następujące wymagania wstępne:
* Musisz mieć dostępną **nazwę dzierżawy CMS**. Poniżej przedstawiono instrukcje dotyczące znajdowania tej nazwy.
### <a name="configure-image-backend-optional"></a>Konfiguracja wewnętrznej bazy danych obrazu (opcjonalnie)
##### <a name="finding-your-media-base-url"></a>Znajdowanie podstawowego adresu URL nośnika
*Uwaga: aby można było wykonać ten krok, należy ukończyć **Konfigurowanie witryny**.*
1. Zaloguj się do narzędzia zarządzania oddziałem, używając wcześniej zanotowanego adresu URL.
1. Otwórz witrynę **Fabrikam** .
1. Kliknij opcję **Składniki majątku** w menu po lewej stronie.
1. Wybierz dowolny składnik majątku dla pojedynczego obrazu.
1. Znajdź **publiczny adres URL** z Inspektora właściwości po prawej stronie. Zawiera on adres URL.
    * Przykład adresu URL: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC
1. Zastąp ostatni identyfikator w adresie URL (MA1nQC w przykładowym adresie URL powyżej) następującym ciągiem: **search?fileName=**
    * Przykładowy adres URL po zamianie: https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=
    * To jest podstawowy **adres URL nośnika** — należy go zanotować.
##### <a name="updating-the-media-base-url"></a>Aktualizowanie podstawowego adresu URL nośnika
1. Zaloguj się do środowiska (HQ)
1. Korzystając z menu po lewej stronie, przejdź do **Moduły > Retail > Ustawienia kanału > Profil kanału**.
1. Kliknij przycisk **Edytuj**.
1. W opcji **właściwości profilu** zamień wartość właściwości **podstawowy adres URL serwera nośnika** na **podstawowy adres URL nośnika**, który utworzono wcześniej.
1. Wybierz drugi kanał z listy po lewej stronie, w obszarze kanał **Domyślny**.
1. W obszarze **właściwości profilu** kliknij opcję **+Dodaj**.
1. Dla właściwości, która została dodana, wybierz **podstawowy adres URL nośnika** jako klucz właściwości i dla wartości właściwości, wprowadź **podstawowy adres URL nośnika**, który utworzono wcześniej.
1. Kliknij przycisk **Zapisz**.

### <a name="configure-email-server-optional"></a>Konfiguruj serwer poczty e-mail (opcjonalnie)
Należy zauważyć, że wprowadzony tutaj serwer SMTP lub usługa poczty e-mail musi być dostępna z poziomu subskrypcji Azure używanej dla środowiska.
1. Zaloguj się do środowiska (HQ)
1. Korzystając z menu po lewej stronie, przejdź do **Moduły > Retail > Ustawienia centrali > Parametry > Parametry poczty e-mail**.
1. Kliknij kartę **Ustawienia SMTP**.
1. W polu **Serwer poczty wychodzącej** wpisz nazwę FQDN lub adres IP serwera SMTP lub usługi poczty e-mail.
1. W polu **numer portu SMTP** wprowadź numer portu (domyślnie jest to 25, jeśli nie jest używany protokół SSL).
1. W polu **nazwa użytkownika** wpisz wartość (jeśli jest wymagane uwierzytelnianie).
1. W polu **hasło** wpisz wartość (jeśli jest wymagane uwierzytelnianie).
1. Kliknij przycisk **Zapisz**.
1. Kliknij przycisk **Odśwież**.
1. Kliknij kartę **Testowa wiadomość e-mail**.
1. W polu dostawca poczty e-mail wybierz opcję **SMTP**.
1. W polu **Wyślij do** wprowadź adres e-mail, pod który ma zostać dostarczona testowa wiadomość e-mail.
1. Kliknik **Wyślij testową wiadomość e-mail**.
### <a name="configure-email-templates-optional"></a>Konfiguruj szablon poczty e-mail (opcjonalnie)
Szablon wiadomości e-mail dla każdego zdarzenia transakcyjnego, który ma być wysłany do wiadomości e-mail, musi zostać zaktualizowany za pomocą prawidłowego adresu e-mail nadawcy.
1. Korzystając z menu po lewej stronie, przejdź do **Moduły > Administrowanie organizacją > Ustawienia > Parametry > Szablony wiadomości e-mail organizacji**.
1. Kliknij opcję **Pokaż listę**.
1. Dla każdego z szablonów z listy:
    1. W polu **Adres e-mail nadawcy** wpisz adres e-mail nadawcy dla tego szablonu wiadomości e-mail.
    1. (opcjonalne) W polu **Nazwa nadawcy** wpisz nazwę, która będzie używana jako nadawca dla tego szablonu wiadomości e-mail.
1. Kliknij przycisk **Zapisz**.
### <a name="customizing-email-templates-optional"></a>Dostosowywanie szablonu poczty e-mail (opcjonalnie)
Można dostosować szablony wiadomości e-mail, tak aby używały różnych obrazów, lub zaktualizować łącza w szablonie w celu połączenia z powrotem ze środowiskiem podglądu. W poniższych krokach opisano sposób pobierania szablonów domyślnych, dostosowywania ich i aktualizowania szablonów w systemie.
1. Za pomocą przeglądarki pobierz [Microsoft Dynamics 365 Commerce wersja zapoznawcza - domyślne szablony wiadomości e-mail plik .zip](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) zawierający następujące dokumenty HTML na komputer lokalny.
    1. Szablon potwierdzenia zamówienia
    1. Wystaw szablon karty upominkowej
    1. Szablon nowego zamówienia
    1. Zapakuj szablon zamówienia
    1. Wybierz szablon zamówienia
1. Szablony dostosowuje się za pomocą edytora tekstów lub HTML. Zobacz listę obsługiwanych tokenów poniżej.
1. Zaloguj się do środowiska (HQ)
1. Korzystając z menu po lewej stronie, przejdź do **Moduły > Retail > Ustawienia centrali > Parametry > Szablony wiadomości e-mail organizacji**.
1. Aby wyświetlić wszystkie szablony, należy rozwinąć listę po lewej stronie.
1. Dla każdego szablonu, który chcesz dostosować, należy wykonać następujące kroki:
    1. Wybierz szablon z listy.
    1. W obszarze **Zawartość wiadomości e-mail** wybierz odpowiednią wersję językową z listy (domyślna **en-us**).
    1. W obszarze **zawartość wiadomości e-mail** kliknij przycisk **Edytuj**, a następnie przejdź do otwartego okienka **Przekaż szablon wiadomości e-mail**.
    1. Kliknij przycisk **Przeglądaj** i zlokalizuj plik HTML z dostosowaną zawartością.
    1. Kliknij przycisk **Przekaż**, szablon zostanie przekazany do systemu i zostanie wyświetlony podgląd.
    1. Kliknij przycisk **OK**.
    1. (Opcjonalne) Dostosuj właściwość **Temat** szablonu.
    1. Kliknij przycisk **Zapisz**.

#### <a name="supported-tokens-in-the-email-template"></a>Obsługiwane tokeny w szablonie wiadomości e-mail
Te tokeny zostaną zastąpione w czasie renderowania poczty e-mail przy użyciu rzeczywistych wartości, które dotyczą odbiorcy i jego zamówienia.

**Zamówienie sprzedaży** — poniższe tokeny mają zastosowanie do całego zamówienia sprzedaży.

|Nazwa tokena|Token |
|---|---|
|Numer zamówienia|%salesid%|
|Nazwa odbiorcy|%customername%|
|Adres dostawy|%deliveryaddress%|
|Adres do faktury|%customeraddress%|
|Data zamówienia|%shipdate%|
|Metoda dostawy|%modeofdelivery%|
|Dyskonto|%discount%|
|Podatek|%tax%|
|Suma zamówienia|%total%|

**Wiersz sprzedaży** — dla każdego produktu w zamówieniu wypełniane są następujące tokeny.

*Uwaga: Umieść tokeny **Lista produktów — start** i **Lista produktów — koniec** na początku i na końcu bloku HTML, który powtarza się dla każdego produktu.*

|Nazwa tokena|Token |
|---|---|
|Lista produktów - start|\<!--%tablebegin.salesline% -->|
|Lista produktów - koniec|\<!--%tableend.salesline%-->|
|Nazwa produktu|%lineproductname%|
|Opis|%lineproductdescription%|
|Ilość|%linequantity%|
|Cena wiersza jednostki|%lineprice% (sprawdź)|
|Wszystkie pozycje w wierszu|%linenetamount%|
|rabat wiersza|%linediscount%|
|Data wysyłki|%lineshipdate%|
|Metoda zaopatrzenia|%linedeliverymode%|
|adres dostawy|%linedeliveryaddress%|
|Jednostka sprzedaży dla wiersza|%lineunit%|

