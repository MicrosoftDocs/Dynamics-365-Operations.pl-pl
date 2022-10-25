---
title: Moduł Czat rozwiązania Commerce z Obsługą wielokanałową dla Customer Service
description: W tym artykule opisano moduł czatu rozwiązania Commerce z Obsługą wielokanałową dla Customer Service w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: 99e8b9d66a04390ab70fd1deff9f95fe28bdfae3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690324"
---
# <a name="commerce-chat-with-omnichannel-for-customer-service-module"></a>Moduł Czat rozwiązania Commerce z Obsługą wielokanałową dla Customer Service

[!include [banner](includes/banner.md)]

W tym artykule opisano moduł *czatu rozwiązania Commerce z Obsługą wielokanałową dla Customer Service* w Microsoft Dynamics 365 Commerce.

W wersji Commerce 10.0.29 do biblioteki modułów Commerce dodano nowy moduł czatu rozwiązania Commerce z Obsługą wielokanałową dla Customer Service. Funkcja czatu Commerce umożliwia klientom handlu elektronicznego korzystanie z funkcji czatów w usłudze Dynamics 365 Obsługa wielokanałowa dla Customer Service, w tym obsługa klienta za pośrednictwem prawdziwego przedstawiciela, pomagająca w rozwiązaniu zapytań od klientów oraz pomagać w sprzedaży klientom rozwiązania Commerce.

Funkcja czatu Commerce umożliwia sprzedawcom detalicznym spełnienie następujących celów:

- Zwiększyć spersonalizowaną relację z klientami, aby usprawnić zachowanie klienta.
- Usprawnić obsługę klienta przez integrację agentów ludzkich i botów samoobsługowych.
- Pomóc agentom zyskać doświadczenie w dostępie do profilów odbiorców w czasie rzeczywistym, zamówień i danych zakupu, które pomagają usprawnić działania operacyjne i usprawnić ich obsługę.
- Zwiększyć ogólną satysfakcję klientów w celu zwiększenia sprzedaży.

W ramach funkcji czatu Commerce są dostępne następujące możliwości:

- Czat rozwiązania Commerce z Obsługą wielokanałową dla Customer Service
- Dodanie usługi **Biuro obsługi rozwiązania Commerce** jako karty aplikacji w doświadczeniu agenta w usłudze Dynamics 365 Obsługa wielokanałowa dla Customer Service

## <a name="prerequisites-for-omnichannel-for-customer-service"></a>Wymagania wstępne dotyczące Obsługi wielokanałowej dla Customer Service

Wstępnie konieczne jest skonfigurowanie czatu w widgecie Obsługa wielokanałowa dla Customer Service oraz uzyskanie niektórych parametrów niezbędnych do skonfigurowania interfejsu czatu Commerce. Aby uzyskać instrukcje, zobacz [Konfigurowanie czatu kanału](/dynamics365/customer-service/set-up-chat-widget).

Po skonfigurowaniu czatu za pomocą widgetu Obsługa wielokanałowa dla Customer Service zostanie skonfigurowany skrypt przypominający poniższy przykład.

`<script id="Microsoft_Omnichannel_LCWidget" src="https://oc-cdn-ocprod.azureedge.net/livechatwidget/scripts/LiveChatBootstrapper.js" data-app-id="xxxx-xxx-4be7-bcd5-1d118ecffe1f" data-org-id="5a0e73c0-xxxx-xxxxx-xxx- 76df135f375d" data-org-url="https://xxsxxxxssdb348f-crm.omnichannelengagementhub.com"></script>`

Skopiuj ten skrypt, ponieważ potrzebne będą jego wartości do skonfigurowania modułu czatu.

### <a name="commerce-chat-with-omnichannel-for-customer-service-mandatory-fields"></a>Obowiązkowe pola czatu rozwiązania Commerce z Obsługą wielokanałową dla Customer Service

W poniższej tabeli pokazano wartości skryptów z widgetu Obsługa wielokanałowa dla Customer Service, które są wymagane do skonfigurowania modułu rozwiązania Commerce z Obsługą wielokanałową dla Customer Service.

| Właściwość widgetu | Opis |
| ------------- |--------------|
| Źródło skryptu | Wartość **src** w skrypcie widgetu rozmów. |
| Identyfikator aplikacji danych | Wartość **data-app-id** w skrypcie widgetu rozmów. |
| Identyfikator organizacji danych | Wartość **data-org-id** w skrypcie widgetu rozmów. |
| Adres URL organizacji danych | Wartość **data-org-url** w skrypcie widgetu rozmów. |

## <a name="configure-the-commerce-chat-experience-for-your-e-commerce-site"></a>Konfigurowanie czatu Commerce dla witryny handlu elektronicznego

Jednym z zalecanych sposobów implementacji obsługi czatu dla witryny handlu elektronicznego jest dodanie modułu rozwiązania czatu Commerce z Obsługą wielokanałową dla Customer Service do udostępnionego fragmentu nagłówka używanego na stronach witryny w portalu handlu elektronicznego.

Aby dodać moduł czatu do fragmentu nagłówka witryny w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. W konstruktorze witryn dla swojej witryny, przejdź do **Fragmenty**.
1. Wybierz pozycję **Nowy**.
1. W oknie dialogowym **Wybierz fragment** wybierz moduł **rozwiązania Commerce z Obsługą wielokanałową dla Customer Service**, wprowadź nazwę fragmentu, a następnie wybierz przycisk **OK**.
1. W widoku konturu wybierz gniazdo **łącznika czatu Msdyn365 cs**.
1. W panelu po prawej **Właściwości czatu**, wykonaj następujące kroki:

    1. W polu **Źródło skryptu** wprowadź **src** uzyskaną w skrypcie Obsługa wielokanałowa dla Customer Service.
    1. W polu **Identyfikator aplikacji danych** wprowadź **data-app-id** uzyskaną w skrypcie Obsługa wielokanałowa dla Customer Service.
    1. W polu **Identyfikator organizacji danych** wprowadź **data-org-id** uzyskaną w skrypcie Obsługa wielokanałowa dla Customer Service.
    1. W polu **Adres URL organizacji danych** wprowadź **data-org-url** uzyskaną w skrypcie Obsługa wielokanałowa dla Customer Service.

    ![Tworzenie fragmentu modułu czatu Commerce w konstruktorze witryn Commerce.](media/Commerce-chat-creating-new-fragment.png)

1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **fragmentów** i otwórz fragment nagłówka dla swojej witryny.
1. W gnieździe modułu **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj fragment**.
1. W oknie dialogowym **Wybieranie moduły** wybierz utworzony wcześniej fragment czatu, a następnie kliknij przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

> [!NOTE]
> Aby uzyskać pełną listę parametrów konfiguracji, zobacz [Parametry czatu proaktywnego w module czatu rozwiązania Commerce](chat-proactive-chat-parameters.md).

## <a name="add-commerce-headquarters-as-an-application-tab-for-omnichannel-for-customer-service"></a>Dodawanie centrali Commerce headquarters jako karty aplikacji dla Obsługi wielokanałowej dla Customer Service

Możesz dodać kartę aplikacji dla centrali Commerce headquarters w Obsłudze wielokanałowej dla Customer Service. Następnie prawdziwi przedstawiciele mogą używać interfejsu użytkownika dla interfejsu agenta Obsługi wielokanałowej dla Customer Service, aby w prosty sposób uzyskać dostęp do modułu Dynamics 365 Commerce Customer Service, który wraz z informacjami o zamówieniach sprzedaży zawiera informacje kontekstowe dotyczące odbiorcy. Ponadto agenci działu obsługi klienta mogą składać nowe zamówienia, inicjować zwroty i weryfikować informacje o stanie zamówienia.

### <a name="create-a-new-application-tab-that-loads-commerce-headquarters-in-an-iframe-module"></a>Utwórz nową kartę aplikacji, która ładuje centralę Commerce headquarters w module iFrame 

Aby utworzyć nową kartę aplikacji, która ładuje centralę Commerce headquarters w module iFrame, wykonaj te kroki.

1. Otwórz portal [Power Apps Maker Portal](https://make.powerapps.com).
1. W okienku nawigacji po lewej stronie zaznacz **Aplikacje**.
1. Wybierz **centrum administracyjne obsługi klienta**.
1. Przejdź do **doświadczenia agenta**.
1. W przypadku **szablonów kart aplikacji** wybierz pozycję **Zarządzaj**.
1. Utwórz nową kartę aplikacji w typie **witryny sieci web innej firmy**. Instrukcje znajdziesz w [Zarządzaniu szablonami karty aplikacji](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).
1. W obszarze **Parametry** w polu **Wartość** parametru **adresu URL** wprowadź następujący adres URL, gdzie `<YourOrganizationHeadquartersURL>` i gdzie `<LegalEntityname>` są zastępowane odpowiednimi wartościami. Wielokanałowa obsługa klienta będzie wyświetlać **{AccountNumber}** z kontekstu rozmowy. Dlatego pozostaw pole **{AccountNumber}** takim, jakie jest.

    `https://<YourOrganizationHeadquartersURL>/?mi=MCRCustomerService&cmp=<LegalEntityName>&embedded=true&customerId={AccountNumber}`

1. Pole **Wartość** parametru **danych** należy pozostawić puste.

![Tworzenie karty aplikacji w usłudze Dynamics 365 Obsługa wielokanałowa dla Customer Service.](media/OC-CS-Admin-Application-Tab-Parameters.png)

## <a name="enable-a-new-application-tab-for-customer-agents-in-dynamics-365-omnichannel-for-customer-service"></a>Włączanie nowej karty aplikacji dla agentów klienta w systemie Dynamics 365 Obsługa wielokanałowa dla Customer Service

Aby włączyć nową kartę aplikacji dla agentów klienta w systemie Dynamics 365 Obsługa wielokanałowa dla Customer Service, wykonaj te kroki.
    
1. Otwórz portal [Power Apps Maker Portal](https://make.powerapps.com).
1. W okienku nawigacji po lewej stronie zaznacz **Aplikacje**.
1. Wybierz **centrum administracyjne obsługi klienta**.
1. Przejdź do **Obsługa klienta \> Strumienie pracy**.
1. Otwórz strumień pracy utworzony dla agentów, a następnie w obszarze **Ustawienia zaawansowane** wybierz opcję **Sesje domyślne**.
1. W obszarze **Karty aplikacji** wybierz kartę **Dodaj istniejącą kartę aplikacji**, a następnie dodaj nową kartę aplikacji utworzoną wcześniej. Dzięki temu będzie wyświetlana karta aplikacji, która ładuje centralę Commerce headquarters w module iFrame, gdy agent otrzyma przychodzący czat z witryny sieci web handlu elektronicznego.

> [!NOTE]
> Nie można zmodyfikować domyślnego szablonu sesji czatu w obrębie strumienia pracy. Z tego względu możesz zdecydować się na utworzenie nowego szablonu lub zduplikowanie istniejącego szablonu w celu jego zaktualizowania. Aby uzyskać więcej informacji, zobacz [Kojarzenie szablonów ze strumieniem pracy](/dynamics365/app-profile-manager/associate-templates).

## <a name="add-context-variables-in-dynamics-365-omnichannel-for-customer-service"></a>Dodawanie zmiennych kontekstowych w usłudze Dynamics 365 Obsługa wielokanałowa dla Customer Service

Aby dodać zmienne kontekstowe w usłudze Dynamics 365 Obsługa wielokanałowa dla Customer Service, wykonaj te kroki.

1. Otwórz portal [Power Apps Maker Portal](https://make.powerapps.com).
1. W okienku nawigacji po lewej stronie zaznacz **Aplikacje**.
1. Wybierz **centrum administracyjne obsługi klienta**.
1. Przejdź do **Obsługa klienta \> Strumienie pracy**.
1. Otwórz strumień pracy utworzony dla agentów, a następnie w obszarze **Ustawienia zaawansowane**, przejdź do obszaru **Zmienne kontekstowe**.
1. Wybierz pozycję **Edytuj**, a następnie dodaj wartość **AccountNumber** jako zmienną kontekstową typu **tekst**. Ta zmienna pomaga w ładowaniu informacji o odbiorcy przez centralę Commerce Headquarters z pasującymi numerami kont.

> [!NOTE]
> Aby odczytać adresy e-mail i nazwy zalogowanych użytkowników z kanału handlu elektronicznego, oprócz zmiennej kontekstowej **AccountNumber** można dodać jako zmienne kontekstowe **E-mail** i **Nazwa** jako typ **Tekst**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie funkcji czatu rozwiązania Commerce](commerce-chat-overview.md)

[Czat rozwiązania Commerce z modułem Power Virtual Agents](chat-module-pva.md)

[Parametry czatu proaktywnego w module czatu rozwiązania Commerce](chat-proactive-chat-parameters.md)
