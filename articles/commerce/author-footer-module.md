---
title: Moduł stopki
description: W tym temacie opisano moduły stopki i sposób ich tworzenia w Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697320"
---
# <a name="footer-module"></a>Moduł stopki  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły stopki i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł stopki jest specjalnym kontenerem używanym do obsługi modułów wyświetlanych w stopce strony. Na przykład może zawierać łącza do różnych stron w witrynie, takie jak **Skontaktuj się z nami** czy **Zasady sklepu**.

## <a name="footer-module-properties"></a>Właściwości modułu stopki 

Podobnie jak większość kontenerów, moduł stopki obsługuje właściwości nagłówka i szerokości. Ponadto obsługuje on dodawanie wielu modułów kategorii stopki. Każdy dodany moduł kategorii stopki jest renderowany jako kolumna w module stopki.

## <a name="modules-available-in-a-footer-module"></a>Moduły dostępne w module stopki

**Elementy stopki** — moduł elementów stopki może zawierać nagłówek, obraz i łącze. Nagłówek może być używany zarówno osobno, jak i w połączeniu z obrazem i łączem. Każde łącze w stopce może być skonfigurowane w taki sposób, aby zawierało tylko tekst (na przykład łącza „Skontaktuj się z nami” i „Polityka prywatności”) lub tak, aby zawierał zarówno tekst, jak i obraz (na przykład łącza do nośników społecznościowych).

**Powrót do początku** — powrót do początku modułu stanowi łącze umożliwiającego szybką nawigację do góry strony. Wymagany jest cel. Domyślną wartością docelową jest #, co zabiera użytkownika na początek strony.

## <a name="author-a-footer-module"></a>Tworzenie modułu stopki

1. W okienku nawigacji wybierz pozycję **Fragmenty**, a następnie wybierz opcję **Nowy fragment strony**.
1. W oknie dialogowym **Nowy fragment strony** wybierz moduł stopki, wprowadź nazwę dla fragmentu strony, a następnie kliknij przycisk **OK**.
1. W drzewie konspektu z lewej strony wybierz przycisk wielokropka (**...**) dla modułu stopki, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł kategorii stopki i wybierz przycisk **OK**.
1. W drzewie konspektu wybierz przycisk wielokropka dla kategorii stopki, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł elementu stopki i wybierz przycisk **OK**.
1. W drzewie konspektu wybierz moduł elementu stopki. Następnie w okienku właściwości po prawej stronie skonfiguruj nagłówek, łącze i tekst łącza oraz obraz w miarę potrzeb.
1. Aby dodać więcej elementów, pwtórz kroki od 5 do 7.
1. Aby dodać łącze „powrót do góry” w drzewie konspektu wybierz przycisk wielokropka dla kategorii stopki, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł powrót do góry i wybierz przycisk **OK**.
1. W drzewie konspektu wybierz moduł powrót do góry. Następnie w okienku właściwości po prawej stronie należy skonfigurować moduł powrót do góry w miarę potrzeb
1. Zapisz fragment strony, zaewidencjonuj go i opublikuj.

Na każdym szablonie strony utworzonym dla witryny wykonaj następujące kroki.

1. W **Głównym** gnieździe na stronie domyślnej w module stopki dodaj fragment stopki, który został utworzony.
1. Zapisz szablon, zaewidencjonuj go i opublikuj.

Dodanie fragmentu strony do szablonów stron pomaga zagwarantować, że stopka będzie renderowana na każdej stronie.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
