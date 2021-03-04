---
title: Dodawanie wiadomości powitalnej
description: W tym temacie opisano sposób dodawania wiadomości powitalnej do witryny sieci Web Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d2a125b4e71016ad620f128af2e3c9f29aa04f4c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414893"
---
# <a name="add-a-welcome-message"></a>Dodawanie wiadomości powitalnej


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób dodawania wiadomości powitalnej do witryny sieci Web Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Wiadomość powitalna witryny e-Commerce może informować odwiedzających o trwającej sprzedaży, aktualizacjach witryn lub dostępności zbiorów sezonowych Wiadomość powitalna jest ustawiana za pomocą modułu alertów.

Moduł alertów powinien zostać dodany do gniazda **komunikatów o błędach/informacjach** w fragmencie nagłówka. Moduł alertów umożliwia określenie wyświetlanego tekstu, koloru tekstu i wyrównania. Pozwala również określić, czy odwiedzający witrynę mogą odrzucić wiadomość.

Gdy wiadomość powitalna zostanie dodana do udostępnionego fragmentu nagłówka, będzie wyświetlana na każdej stronie korzystającej z szablonu, w którym używany jest ten udostępniony fragment nagłówka.

Aby dodać wiadomość powitalną do witryny, wykonaj następujące kroki.

1. Przejdź do swojej witryny w module konstruktora witryn Commerce.
1. Wybierz **Fragmenty**.
1. Wybierz fragment nagłówka, do którego ma zostać dodana wiadomość.
1. W drzewie konspektu rozwiń **komunikaty o błędach/informacjach**.
1. Wybierz moduł alertów, a następnie kliknij przycisk **OK**. Jeśli moduł alertów jeszcze nie istnieje, najpierw wybierz przycisk wielokropka (**...**) obok **komunikaty o błędach/informacjach**, a następnie wybierz opcję **Dodaj moduł**.
1. W okienku właściwości po prawej stronie na karcie **Dane** wybierz pozycję **Dodaj źródło danych**, a następnie wybierz pozycję **Zawartość**.
1. W polu **wpisany tekst** wprowadź tekst komunikatu powitalnego.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment nagłówka, a następnie wybierz opcję **Publikuj**, aby ją opublikować. 

Komunikat powitalny będzie teraz wyświetlany u góry każdej strony witryny, która używa wybranego fragmentu nagłówka.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie logo](add-logo.md)

[Wybór motywu witryny](select-site-theme.md)

[Praca z plikami zastępowania CSS](css-override-files.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]