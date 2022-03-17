---
title: Konfigurowanie środowisk usługi i połączonych aplikacji
description: Ten temat zawiera informacje dotyczące konfigurowania środowisk serwisowych i połączonych aplikacji.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c3366e75b4a6d3f33a1aac9e444236d9ae57c829
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371735"
---
# <a name="configure-service-environments-and-connected-applications"></a>Konfigurowanie środowisk usługi i połączonych aplikacji

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące konfigurowania środowisk serwisowych i połączonych aplikacji. Ten proces to trzy kroki. Krok 1 jest obowiązkowy, a kroki 2 i 3 są opcjonalne.

## <a name="step-1-create-a-service-environment"></a>Krok 1: Tworzenie środowiska usługi

Podczas tworzenia środowiska usług zdefiniuj listę użytkowników, którzy mogą wdrażać w nim funkcje globalizacji. Opcjonalnie w przypadku niektórych scenariuszy zdefiniuj listę zewnętrznych aplikacji, które mogą się komunikować z usługą fakturowania elektronicznego. Skonfiguruj sekwencje numerów, jeśli będą one używać w scenariuszach.

Aby zakończyć ten krok, zobacz [Środowiska usług](e-invoicing-service-environments.md).

## <a name="step-2-add-certificates-and-secrets"></a>Krok 2: Dodaj certyfikaty i tajemnice

Dodaj odwołanie do klucza Microsoft Azure i kopii, aby użyć ich w scenariuszach. Ten krok jest obowiązkowy, jeśli akcje w potokach przetwarzania używają certyfikatów i kluczy tajnych do podpisywania cyfrowego lub komunikacji z zewnętrznymi usługami sieciowymi.

Aby zakończyć ten krok, zobacz [certyfikaty odbiorcy i instrukcje](e-invoicing-customer-certificates-secrets.md).

## <a name="step-3-configure-connected-applications"></a>Krok 3: Konfigurowanie połączonych aplikacji

Aby skonfigurować komunikację między aplikacjami Dynamics 365 Finance lub Dynamics 365 Supply Chain Management a fakturowaniem elektronicznym, należy skonfigurować Finance lub Supply Chain Management, aby skonstruować wywołanie usługi fakturowania elektronicznego i przygotować dane biznesowe w ujednoliconej strukturze, którą można przekształcić w wymagany format elektroniczny. Aplikacje muszą również poprawnie przetwarzać odpowiedzi z usługi. Konfigurację można ukończyć bezpośrednio w środowisku zarządzania finansami lub Supply Chain Management albo w usłudze Regulatory Configuration Service (RCS). Po zakończeniu konfigurowania z RCS można ją wdrożyć w środowisku zarządzania finansami lub Supply Chain Management. W tym kroku należy zarejestrować połączną aplikację w celu wdrożenia parametrów.

Aby zakończyć ten krok, zobacz [Połączone aplikacje](e-invoicing-connected-applications.md).
