---
title: Dodawanie logo
description: W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914631"
---
# <a name="add-a-logo"></a>Dodawanie logo

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać logo do witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Podczas kompilowania witryny jedną z pierwszych rzeczy, którą prawdopodobnie będzie zrobić, będzie dodanie logo firmy lub marki do nagłówka witryny. Zestaw startowy online Dynamics 365 Commerce oferuje moduł, który ułatwia to zadanie.

Możesz dodać logo bezpośrednio do szablonu, układu lub strony. W ten sposób można łatwo zmienić logo, które pojawia się na określonych stronach lub grupach stron. W tym temacie omówiono jednak najczęstszy scenariusz dodawania logo do fragmentu nagłówka, który można ponownie wykorzystać na wszystkich stronach witryny.

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było dodać logo do wszystkich stron witryny, należy wykonać następujące zadania.

1. Przekaż logo do menedżera cyfrowych elementów zawartości, do którego możesz uzyskać dostęp ze strony **Elementy zawartości**.
1. Utwórz fragment nagłówka. Aby uzyskać więcej informacji na temat tworzenia i używania fragmentów, zobacz [Praca z fragmentami](work-with-fragments.md).
1. Dołącz fragment nagłówka w szablonie, którego strony witryny używają do ustawiania opcji układu i modułu. Aby uzyskać więcej informacji na temat szablonów, zobacz [Praca z szablonami](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Dodawanie logo do fragmentu nagłówka

Aby dodać logo do fragmentu nagłówka witryny, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Fragmenty**, a następnie wybierz utworzony fragment nagłówka.
2. Wybierz **Wyewidencjonuj**.
3. Rozwiń gniazdo **Nagłówek** i gniazdo **Logo**.
4. Wybierz przycisk wielokropka (**...**) dla gniazda **Logo**, a następnie wybierz opcję **Dodaj moduł**.
5. Wybierz moduł logo.
6. W okienku właściwości po prawej stronie skonfiguruj moduł logo, aby zostało ono wyświetlone.
7. Zapisz fragment nagłówka, zaewidencjonuj go i opublikuj.

Po opublikowaniu zaktualizowanego fragmentu nagłówka wszystkie strony witryny, które używają szablonu zawierającego fragment nagłówka, będą zawierać Twoje logo.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wybór motywu witryny](select-site-theme.md)

[Praca z plikami zastępowania CSS](css-override-files.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie wiadomości powitalnej](add-welcome-message.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)

