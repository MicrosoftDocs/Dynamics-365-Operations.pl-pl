---
title: Dodawanie logo
description: W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 073c3d6f8d5ee88d51efb41f6b9c1a204b82fa12
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980314"
---
# <a name="add-a-logo"></a>Dodawanie logo

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Podczas kompilowania witryny jedną z pierwszych rzeczy, którą prawdopodobnie będzie zrobić, będzie dodanie logo firmy lub marki do nagłówka witryny. Biblioteka modułów online Dynamics 365 Commerce oferuje moduł, który ułatwia to zadanie.

Możesz dodać logo bezpośrednio do szablonu, układu lub strony. W ten sposób można łatwo zmienić logo, które pojawia się na określonych stronach lub grupach stron. W tym temacie omówiono jednak najczęstszy scenariusz dodawania logo do fragmentu nagłówka, który można ponownie wykorzystać na wszystkich stronach witryny.

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było dodać logo do wszystkich stron witryny, należy wykonać następujące zadania.

1. Przekaż swoją logo do biblioteki multimediów.
1. Utwórz fragment nagłówka. Aby uzyskać więcej informacji na temat tworzenia i używania fragmentów, zobacz [Praca z fragmentami](work-with-fragments.md).
1. Dołącz fragment nagłówka w szablonie, którego strony witryny używają do ustawiania opcji układu i modułu. Aby uzyskać więcej informacji na temat szablonów, zobacz [Praca z szablonami](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Dodawanie logo do fragmentu nagłówka

Aby dodać logo do fragmentu nagłówka witryny, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.
1. Wybierz utworzony fragment nagłówka, a następnie wybierz opcję **Edytuj**.
1. Rozwiń moduł nagłówka.
1. W okienku właściwości modułu nagłówka wprowadź obraz i łącze do logo. 
1. Zapisz fragment nagłówka, zakończ jego edycję, a następnie go opublikuj.

Po opublikowaniu zaktualizowanego fragmentu nagłówka wszystkie strony witryny, które używają szablonu zawierającego fragment nagłówka, będą zawierać Twoje logo.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wybór motywu witryny](select-site-theme.md)

[Praca z plikami zastępowania CSS](css-override-files.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie wiadomości powitalnej](add-welcome-message.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)

