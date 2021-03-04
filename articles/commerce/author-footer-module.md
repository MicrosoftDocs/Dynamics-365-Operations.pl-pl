---
title: Moduł stopki
description: W tym temacie opisano moduły stopki i sposób ich tworzenia w Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 42a71ea9498461febca80952acc3158517918332
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414921"
---
# <a name="footer-module"></a>Moduł stopki  

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły stopki i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł stopki jest specjalnym kontenerem używanym do obsługi modułów wyświetlanych w stopce strony. Na przykład może zawierać łącza do różnych stron w witrynie, takie jak **Skontaktuj się z nami** czy **Zasady sklepu**.

Poniższy obraz pokazuje przykład modułu stopki na stronie witryny.

![Przykład modułu stopki](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Właściwości modułu stopki 

Podobnie jak większość kontenerów, moduł stopki obsługuje właściwości nagłówka i szerokości. Ponadto obsługuje on dodawanie wielu modułów kategorii stopki. Każdy dodany moduł kategorii stopki jest renderowany jako kolumna w module stopki.

## <a name="modules-available-in-a-footer-module"></a>Moduły dostępne w module stopki

**Elementy stopki** — moduł elementów stopki może zawierać nagłówek, obraz i łącze. Nagłówek może być używany zarówno osobno, jak i w połączeniu z obrazem i łączem. Każde łącze w stopce może być skonfigurowane w taki sposób, aby zawierało tylko tekst (na przykład łącza „Skontaktuj się z nami” i „Polityka prywatności”) lub tak, aby zawierał zarówno tekst, jak i obraz (na przykład łącza do nośników społecznościowych).

**Powrót do początku** — powrót do początku modułu stanowi łącze umożliwiającego szybką nawigację do góry strony. Wymagany jest cel. Domyślną wartością docelową jest \#, co zabiera użytkownika na początek strony.

## <a name="create-a-footer-module"></a>Tworzenie modułu stopki

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Nowy fragment** wybierz moduł **Kontener**, wprowadź nazwę dla fragmentu, a następnie kliknij przycisk **OK**.
1. W gnieździe **Domyślny kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Kategorii stopki** i wybierz przycisk **OK**.
1. W gnieździe **Kategoria stopki** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Element stopki** i wybierz przycisk **OK**.
1. Wybierz gniazdo **Element stopki**, a następnie w okienku właściwości po prawej stronie skonfiguruj nagłówek, łącze i tekst łącza oraz obraz w miarę potrzeb.
1. Aby dodać więcej elementów, pwtórz kroki od 5 do 7 dla każdego elementu.
1. Aby dodać łącze „powrót do góry” w drzewie konspektu wybierz wielokropek (**...**) w gnieździe **Kategoria stopki**, a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Powrót do góry** i wybierz przycisk **OK**.
1. Wybierz gniazdo **Powrót do góry**, a następnie w okienku właściwości po prawej stronie skonfiguruj tekst i inne właściwości modułu w miarę potrzeb.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby go opublikować.

Aby zagwarantować, że nagłówek ma się pojawiać na każdej stronie, należy wykonać poniższe kroki na każdym szablonie strony utworzonym dla witryny.

1. W gnieździe **Stopka** w module **Strona domyślna** dodaj fragment stopki, który został utworzony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

Dodanie fragmentu do szablonów stron pomaga zagwarantować, że stopka będzie renderowana na każdej stronie.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]