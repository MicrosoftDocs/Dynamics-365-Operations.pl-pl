---
title: Czat rozwiązania Commerce z modułem usługi Power Virtual Agents
description: W tym artykule opisano czat rozwiązania Commerce z modułem usługi Power Virtual Agents, który integruje usługę Microsoft Power Virtual Agents z witrynami internetowymi aplikacji Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-07
ms.openlocfilehash: 838990cb638479c9c90ba0e38794ecedd55e95b3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691081"
---
# <a name="commerce-chat-with-power-virtual-agents-module"></a>Czat rozwiązania Commerce z modułem usługi Power Virtual Agents

[!include [banner](includes/banner.md)]

W tym artykule opisano czat rozwiązania Commerce z modułem usługi Power Virtual Agents, który integruje usługę Microsoft Power Virtual Agents z witrynami internetowymi aplikacji Dynamics 365 Commerce.

Funkcja czatu rozwiązania Commerce z modułem usługi Power Virtual Agents umożliwia klientom handlu elektronicznego rozwiązania Dynamics 365 używanie możliwości czatbotów usługi Power Virtual Agents do obsługi zapytań. Od wydania Dynamics 365 Commerce 10.0.30 tę funkcję można dodawać witryn internetowych handlu elektronicznego za pomocą czatu rozwiązania Commerce z modułem usługi Power Virtual Agents, który jest częścią biblioteki modułów Commerce.

Funkcja czatu rozwiązania Commerce z usługą Power Virtual Agents pomaga firmom osiągnąć następujące cele:

- Zwiększenie spersonalizowanej relacji z konsumentami oraz liczby zachowywanych klientów.
- Usprawnienie obsługi klienta przez integrację czatbotów samoobsługowych.
- Zwiększenie ogólnej satysfakcji klientów i w wyniku tego zwiększenie sprzedaży.

> [!NOTE]
> Aby poznać różnice między aplikacjami Obsługa wielokanałowa dla Customer Service oraz Power Virtual Agents w rozwiązaniu Dynamics 365 zobacz [Omówienie modułów czatu rozwiązania Commerce](/commerce-chat-modules-overview.md).

## <a name="prerequisites-for-using-power-virtual-agents"></a><a id="prereq"></a>Wymagania wstępne dotyczące korzystania z usługi Power Virtual Agents

Aby korzystać z funkcji czatu rozwiązania Commerce z usługą Power Virtual Agents, należy najpierw utworzyć czatbota Power Virtual Agents dla witryny internetowej handlu elektronicznego. Aby uzyskać instrukcje, zobacz [Tworzenie bota usługi Power Virtual Agent](/power-virtual-agents/authoring-first-bot).

Po skonfigurowaniu czatbota musisz skopiować wartości parametrów czatbota **Identyfikator bota** i **Identyfikator dzierżawcy**, aby skonfigurować środowisko czatu rozwiązania Commerce. Aby uzyskać informacje dotyczące sposobu kopiowania tych wartości, zobacz [Pobieranie parametrów bota usługi Power Virtual Agents](/power-virtual-agents/publication-connect-bot-to-custom-application#retrieve-your-power-virtual-agents-bot-parameters).

## <a name="configure-your-e-commerce-site"></a>Konfigurowanie witryny handlu elektronicznego 

Jednym z zalecanych sposobów implementacji obsługi czatu dla witryny handlu elektronicznego jest dodanie modułu rozwiązania czatu Commerce z modułem Power Virtual Agents do udostępnionego fragmentu nagłówka używanego na stronach witryny.

Aby dodać moduł czatu do fragmentu nagłówka witryny w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. W konstruktorze witryn rozwiązania Commerce dla swojej witryny przejdź do obszaru **Fragmenty**.
1. Wybierz pozycję **Nowy**.
1. W oknie dialogowym **Wybieranie fragmentu** wybierz moduł **Czat rozwiązania Commerce z usługą Power Virtual Agents** wprowadź nazwę fragmentu, a następnie wybierz przycisk **OK**.
1. W widoku konturu wybierz gniazdo **konektora czatu PVA Msdyn365**.
1. W okienku właściwości po prawej stronie wykonaj następujące kroki:

    1. W obszarze **Parametry bota** w polu **Adres URL usługi CDN dla czatu internetowego w usłudze Bot Framework** pozostaw wartość domyślną (na przykład `https://cdn.botframework.com/botframework-webchat/latest/webchat.js`).
    1. W polu **Adres uwierzytelniania usługi Bot Framework Direct Line** pozostaw wartość domyślną (na przykład `https://powerva.microsoft.com/api/botmanagement/v1/directline/directlinetoken`).
    1. W polu **Identyfikator bota** wprowadź wartość z usługi Power Virtual Agents dla **identyfikatora bota** skopiowaną w sekcji [Wymagania wstępne dotyczące korzystania z usługi Power Virtual Agents](#prereq).
    1. W polu **Identyfikator dzierżawcy** wprowadź skopiowaną wartość **Identyfikator dzierżawcy**.

1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **fragmentów** i otwórz fragment nagłówka dla swojej witryny.
1. W gnieździe modułu **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj fragment**.
1. W oknie dialogowym **Wybieranie moduły** wybierz utworzony wcześniej fragment czatu, a następnie kliknij przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="proactive-chat-parameters"></a>Parametry proaktywnego czatu

Aby uzyskać pełną listę parametrów konfiguracji proaktywnego czatu, zobacz [Parametry czatu proaktywnego w module czatu rozwiązania Commerce](chat-proactive-chat-parameters.md).

> [!NOTE]
> Obecnie usługa Power Virtual Agents nie obsługuje uwierzytelniania Azure Active Directory B2C (Azure AD B2C). Obsługuje ona tylko anonimowe wywołania Retail Cloud Scale Unit (RCSU) w celu pobrania dostępności produktu lub interakcji z innymi anonimowymi interfejsami API. Wywołania uwierzytelnionych interfejsów API za pośrednictwem czatbotów usługi Power Virtual Agents wymagają jawnego zalogowania się klienta.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie funkcji czatu rozwiązania Commerce](commerce-chat-overview.md)

[Moduł Czat rozwiązania Commerce z Obsługą wielokanałową dla Customer Service](commerce-chat-module.md)

[Parametry czatu proaktywnego w module czatu rozwiązania Commerce](chat-proactive-chat-parameters.md)
