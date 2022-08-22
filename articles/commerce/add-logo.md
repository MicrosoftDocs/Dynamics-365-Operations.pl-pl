---
title: Dodawanie logo
description: W tym artykule opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 4bd47907791edfd0ab81282bd1e465ac54172cdf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278105"
---
# <a name="add-a-logo"></a>Dodawanie logo

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.

Podczas kompilowania witryny jedną z pierwszych rzeczy, którą prawdopodobnie będzie zrobić, będzie dodanie logo firmy lub marki do nagłówka witryny. Biblioteka modułów online Dynamics 365 Commerce oferuje moduł, który ułatwia to zadanie.

Możesz dodać logo bezpośrednio do szablonu, układu lub strony. W ten sposób można łatwo zmienić logo, które pojawia się na określonych stronach lub grupach stron. W tym artykule omówiono jednak najczęstszy scenariusz dodawania logo do fragmentu nagłówka, który można ponownie wykorzystać na wszystkich stronach witryny.

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

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
