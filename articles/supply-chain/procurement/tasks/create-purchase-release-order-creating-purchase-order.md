--- 
title: "Tworzenie zlecenia wydania zakupu podczas tworzenia zamówienia zakupu"
description: "W tej procedurze pokazano sposób korzystania z umowy zakupu podczas tworzenia zamówienia zakupu."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 194d811da09c746167bd9489ce39ae6a6f810ec0
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-release-order-when-creating-the-purchase-order"></a>Tworzenie zlecenia wydania zakupu podczas tworzenia zamówienia zakupu

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób korzystania z umowy zakupu podczas tworzenia zamówienia zakupu. Umowa zakupu musi być stosowana podczas tworzenia zamówienia zakupu, ponieważ istnieją ogólne warunki, które powinny być skopiowane do nagłówka zamówienia zakupu. To zadanie zazwyczaj wykonuje pracownik działu zakupów. Warunkiem wstępnym wykonania zadań z tego przewodnika jest istnienie ważnej umowy zakupu ze zobowiązaniem co do ilości produktu dla dostawcy i towarów. Tej samej procedury można użyć w przypadku umowy zakupu z innymi typami zobowiązań. Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF. Jeśli używasz firmy USMF, można najpierw wykonać zadania z przewodnika „Tworzenie umowy zakupu” i skonfigurować warunki wstępne konieczne dla tego przewodnika.


## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu
1. Otwórz obszar roboczy Przygotowanie zamówienia zakupu.
2. Kliknij opcję Nowe zamówienie zakupu.
3. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. Przełącz rozwinięcie sekcji Ogólne.
7. W polu Umowa zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wszystkie dostępne umowy z dostawcą są wymienione w tym miejscu. Znajdź obowiązującą umowę, której chcesz używać.  
8. Na liście kliknij łącze w wybranym wierszu.
9. Kliknij przycisk Tak.
10. Kliknij przycisk OK.

## <a name="add-a-line"></a>Dodawanie wiersza
1. W polu Numer towaru wpisz wartość.
    * Jeśli w zobowiązaniu istnieją określone wymiary magazynowe lub wymiary lokalizacji, te same wartości należy wprowadzić w wierszu zamówienia zakupu, aby umowa była używana.  
2. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Pole oddziału może już być wypełnione wartością domyślną z zamówienia lub od dostawcy. W takim przypadku pomiń ten krok.  
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. Wprowadź liczbę w polu Ilość.
    * Sprawdź, czy cena została skopiowana ze zobowiązania.  

## <a name="look-up-the-commitment"></a>Wyszukiwanie zobowiązania
1. Kliknij opcję Aktualizuj wiersz.
2. Kliknij opcję Powiązany.
    * W tym miejscu można uzyskać szczegółowe informacje dotyczące umowy zakupu. Na przykład można wyświetlić cenę i sprawdzić, czy cena i rabat są stałe, co oznacza, że jeśli zmienisz cenę lub rabat w zamówieniu zakupu na inną wartość niż podana w zobowiązaniu, system usunie łącze, w związku z czym wiersz zamówienia zakupu nie będzie spełniał zobowiązania. Można również sprawdzić, czy jest zaznaczona opcja Wymuszono maks., która oznacza, że ilość w zobowiązaniu nie może zostać przekroczona po zsumowaniu wszystkich zakupów spełniających zobowiązanie.  
3. Zamknij stronę.

## <a name="look-up-the-purchase-agreement"></a>Wyszukiwanie umowy zakupu
1. W okienku akcji kliknij pozycję Ogólne.
2. Kliknij opcję Umowa zakupu.
3. Zamknij stronę.
4. Zamknij stronę.


