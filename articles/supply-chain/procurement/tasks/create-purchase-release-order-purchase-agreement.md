---
title: Zastosowanie umowy zakupu podczas tworzenia zamówienia zakupu
description: W tej procedurze pokazano sposób korzystania z umowy zakupu podczas tworzenia zamówienia zakupu.
author: kamaybac
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 341d3f37936bcca8d8b273894b4a12debfe6eced
ms.sourcegitcommit: 787c94b35f343f4c38fc8efaaa0cfaf20a846368
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2021
ms.locfileid: "6647189"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>Zastosowanie umowy zakupu podczas tworzenia zamówienia zakupu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób korzystania z umowy zakupu podczas tworzenia zamówienia zakupu. Umowa zakupu musi być stosowana podczas tworzenia zamówienia zakupu, ponieważ istnieją ogólne warunki, które powinny być skopiowane do nagłówka zamówienia zakupu. To zadanie zazwyczaj wykonuje pracownik działu zakupów. Warunkiem wstępnym wykonania zadań z tego przewodnika jest istnienie ważnej umowy zakupu ze zobowiązaniem co do ilości produktu dla dostawcy i towarów. Tej samej procedury można użyć w przypadku umowy zakupu z innymi typami zobowiązań.

## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Przejdź do **Produkcja i zaopatrzenie \> Obszary robocze \> Przygotowanie zamówienia zakupu**.
1. W okienku akcji kliknij pozycję **Nowe zamówienie zakupu**.
1. Zostanie otwarte okno dialogowe **Tworzenie zamówienia zakupu**. Wybierz **Konto dostawcy**. W razie potrzeby sprawdź i dostosuj pozostałe pola adresu.
1. Rozwiń skróconą kartę **Ogólne**.
1. W polu **Umowa zakupu** znajdź i wybierz umowę efektywną, która ma być używana. Wszystkie dostępne umowy z dostawcą są wymienione w tym miejscu.  
1. Wybierz opcję **Tak**.
1. Kliknij przycisk **OK**.

## <a name="add-a-line"></a>Dodaj wiersz

1. W polu **Numer towaru** wpisz wartość. Jeśli w zobowiązaniu istnieją określone wymiary magazynowe lub wymiary lokalizacji, te same wartości należy wprowadzić w wierszu zamówienia zakupu, aby umowa była używana.
1. W polu **Oddział** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie. Pole oddziału może już być wypełnione wartością domyślną z zamówienia lub od dostawcy. W takim przypadku pomiń ten krok.  
1. Na liście znajdź i zaznacz odpowiedni rekord.
1. Na liście wybierz łącze w wybranym wierszu.
1. W polu **Ilość** wpisz liczbę. Sprawdź, czy cena została skopiowana ze zobowiązania.  

## <a name="look-up-the-commitment"></a>Wyszukiwanie zobowiązania

1. Wybierz **Aktualizuj wiersz**.
1. Wybierz **Dołączone**. W tym miejscu można uzyskać szczegółowe informacje dotyczące umowy zakupu. Na przykład można wyświetlić cenę i sprawdzić, czy cena i rabat są stałe, co oznacza, że jeśli zmienisz cenę lub rabat w zamówieniu zakupu na inną wartość niż podana w zobowiązaniu, system usunie łącze, w związku z czym wiersz zamówienia zakupu nie będzie spełniał zobowiązania. Można również sprawdzić, czy jest zaznaczona opcja Wymuszono maks., która oznacza, że ilość w zobowiązaniu nie może zostać przekroczona po zsumowaniu wszystkich zakupów spełniających zobowiązanie.  
1. Zamknij stronę.

## <a name="look-up-the-purchase-agreement"></a>Wyszukiwanie umowy zakupu

1. W **okienku akcji** wybierz pozycję **Ogólne**.
1. Wybierz **Umowa zakupu**.
1. Zamknij stronę.
1. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]