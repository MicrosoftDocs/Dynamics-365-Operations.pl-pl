--- 
title: "Definiowanie metody płatności odbiorcy"
description: "Utwórz metodę płatności dla płatności od odbiorców."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: bfafcccb12112ca7cceefb65be3f942bfc307751
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="establish-customer-method-of-payment"></a>Definiowanie metody płatności odbiorcy

[!include[task guide banner](../../includes/task-guide-banner.md)]

Utwórz metodę płatności dla płatności od odbiorców. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Metody płatności.
2. Kliknij przycisk Nowy.
3. W polu Metody płatności wprowadź identyfikator metody płatności.
    * Metoda powiązana z identyfikatorem płatności jest wyświetlana na fakturach i w płatnościach, dlatego musi być na tyle opisowa, aby sugerować, jaki typ płatności jest rejestrowany i dla którego konta bankowego.  
4. W polu Opis wprowadź opis.
5. Wybierz, jaki stan płatności jest wymagany, aby można było księgować płatności.
    * Podczas tworzenia płatności od odbiorcy można ją zaksięgować tylko wtedy, gdy stan płatności jest taki sam jak zdefiniowany tutaj.  
6. Określ, jak mają być tworzone płatności odbiorców za faktury.
    * Ta opcja jest używana tylko przy generowaniu propozycji płatności. Można używać propozycji płatności dla płatności od odbiorców podczas operacji polecenia zapłaty, aby ściągać środki z rachunków bankowych odbiorców.  
7. Wybierz typ płatności.
    * Typ płatności może pomóc określić, czy płatność będzie w jakikolwiek sposób weryfikowana.  
8. Wybierz typ konta, na jakim będą księgowane płatności.
    * Zazwyczaj w tej opcji wybiera się opcję Bank.  
9. Wybierz konto bankowe, na którym ta płatność ma zostać zarejestrowana.
10. Wprowadź typ transakcji bankowej, aby zidentyfikować typu płatności używany przez bank.
    * Typ transakcji bankowej jest używany w procesie uzgadniania konta bankowego i ułatwia uzgadnianie.  
11. Określ, czy ta płatności będzie tymczasowo księgowana na koncie pomostowym.
    * Jeśli chcesz wypróbować określony czas obrotu kasowego dla rozliczania płatności przez bank, użyj funkcji transakcji pomostowej. Płatność tymczasowo zostanie zaksięgowana na koncie księgowym, dopóki bank jej nie rozliczy. Wtedy płatność zostanie przeniesiona na konto bankowe zdefiniowane w tym miejscu.  
12. Wprowadź konto główne używane dla księgowania pomostowego.
    * To jest konto główne, na którym płatność zostanie tymczasowo zaksięgowana, jeśli są używane transakcje pomostowe.  
13. Na karcie Format pliku zdefiniuj ustawienia płatności elektronicznych.
14. Karta Kontrola płatności służy do definiowania pól, które są wymagane.
    * Na przykład jeśli wszystkie płatności z tą metodą płatności mają być wpłacane, można zaznaczyć tę opcję na tej karcie.  
15. Karta Atrybuty płatności służy do określania, które atrybuty płatności mają być używane dla tej metody płatności.
16. Kliknij przycisk Zapisz.

