---
title: Konfiguracja fakturowania elektronicznego
description: W tym artykule omówiono proces ustawiania i konfigurowania fakturowania elektronicznego.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: de94843c1e98a8788375bd41def587a64baea07d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272188"
---
# <a name="electronic-invoicing-setup"></a>Konfiguracja fakturowania elektronicznego

[!include [banner](../includes/banner.md)]

W tym artykule omówiono proces ustawiania i konfigurowania fakturowania elektronicznego. Kroki konfiguracji należy wykonać w podanej kolejności. Jeśli krok jest obowiązkowy, ale go pominiesz, funkcja nie będzie działać poprawnie, a podczas kolejnych kroków lub podczas korzystania z funkcji wystąpi wiele błędów. 

Przed rozpoczęciem upewnij się, że wszystkie główne składniki są poprawnie skonfigurowane, że zarejestrowałeś się w usłudze Regulatory Configuration Service (RCS) i masz wystąpienie RCS oraz że dodatek fakturowania elektronicznego jest zainstalowany dla systemu Microsoft Dynamics 365 Finance lub środowisko Dynamics 365 Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Zarejestruj się i zainstaluj Fakturowanie elektroniczne](e-invoicing-install-add-in-microservices-lcs.md).

Następnie skonfiguruj zasoby systemu Azure, które wymagają fakturowania elektronicznego. Aby uzyskać więcej informacji, zobacz temat [Skonfiguruj zasoby platformy Azure do fakturowania elektronicznego](e-invoicing-set-up-azure-resources.md).

Po skonfigurowaniu głównych komponentów, współpracuj z RCS w celu skonfigurowania głównych komponentów logicznych fakturowania elektronicznego. Najpierw zdefiniuj liczbę środowisk usług, które będzie zachowana. W ten sposób definiujesz partycjonowanie danych logicznych i konfiguracji, aby zapewnić granicę między środowiskiem programistycznym lub testowym a środowiskami produkcyjnymi. Aby skonfigurować proces programowania w sposób elastyczny, możesz potrzebować kilku oddzielnych środowisk programistycznych i testowych. Oprócz definiowania środowisk usług należy ustawić łącze do aplikacji biznesowych, takich jak Finanse lub Supply Chain Management, bezpośrednio z systemu RCS w celu skonfigurowania parametrów wymaganych do poprawnego działania fakturowania elektronicznego. Aby uzyskać więcej informacji o środowiskach, należy zapoznać się z tematem [Środowiska usługowe](e-invoicing-service-environments.md).

Po skonfigurowaniu wszystkiego możesz utworzyć własne funkcje globalizacji, które definiują różne scenariusze przetwarzania dokumentów elektronicznych i przekształcania danych lub importowania dokumentów z repozytorium globalnego. Aby uzyskać więcej informacji na temat pracy z funkcjami globalizacji, zobacz [Praca z funkcjami globalizacji](e-invoicing-working-globalization-features.md).

Jeśli Twoje scenariusze wymagają integracji z pocztą e-mail lub programem SharePoint w celu przetwarzania przychodzących dokumentów elektronicznych, zobacz [Przetwarzanie przychodzących dokumentów elektronicznych](e-invoicing-process-incoming-electronic-documents.md), aby uzyskać informacje na temat konfigurowania i używania tych kanałów.
