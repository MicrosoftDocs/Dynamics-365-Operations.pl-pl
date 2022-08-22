---
title: Dodawanie powiadomienia o prawach autorskich
description: W tym artykule opisano, jak dodać informację o prawach autorskich do swojej witryny e-Commerce.
author: josaw1
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 044fdd958a7233322553c8d9b03163c6ce5c4cb3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270463"
---
# <a name="add-a-copyright-notice"></a>Dodawanie powiadomienia o prawach autorskich

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak dodać informację o prawach autorskich do swojej witryny e-Commerce.

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było dodać do witryny powiadomienie o prawach autorskich, należy dysponować następującymi pozycjami:

- Szablon zawierający wspólny fragment stopki.
- Strona korzystająca z tego szablonu.

## <a name="add-a-copyright-notice"></a>Dodawanie powiadomienia o prawach autorskich

Aby dodać powiadomienie o prawach autorskich na końcu każdej strony korzystającej z określonego szablonu, wykonaj następujące kroki.

1. Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.
1. W oknie dialogowym **Nowy fragment** wybierz moduł **Stopki** i nazwij fragment. Na przykład wprowadź **stopka — prawa autorskie**.
1. Kliknij przycisk **OK**.
1. W okienku nawigacji wybierz przycisk wielokropka (**...**) obok **Stopki**, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym wybierz **Kategoria stopki** i wybierz przycisk **OK**.
1. W okienku nawigacji wybierz przycisk wielokropka (...) obok **Kategoria stopki**, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym wybierz **Blok zaawansowanej zawartości** i wybierz przycisk **OK**.
1. W okienku nawigacji wybierz opcję **Blok aawansowanej zawarości**.
1. W okienku właściwości po prawej stronie w polu **Akapit** dodaj wiadomość dotyczącą praw autorskich. Na przykład wprowadź **(C) Fabrikam 2019**.
1. Wybierz opcję **Zapisz**, wybierz opcję **Zakończ edycję**, a następnie wybierz opcję **Publikuj**.
1. Przejdź do **Szablony**, wybierz szablon, a następnie wybierz opcję **Edytuj**.
1. W obszarze **Konspekt strony** rozwiń węzeł **Treść**, a następnie rozwiń węzeł **Strona domyślna**.
1. Wybierz przycisk wielokropka obok **Gniazdo nagłówka**, a następnie wybierz opcję **Dodaj fragment**.
1. Wybierz utworzony fragment, który utworzono wcześniej, a następnie wybierz opcję **Wybierz**.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Stopka zawierająca informację o prawach autorskich jest automatycznie wyświetlana u dołu wszystkich stron, w których jest używany wybrany szablon.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie logo](add-logo.md)

[Wybór motywu witryny](select-site-theme.md)

[Praca z plikami zastępowania CSS](css-override-files.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
