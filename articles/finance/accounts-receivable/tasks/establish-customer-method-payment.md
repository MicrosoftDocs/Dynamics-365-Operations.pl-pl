---
title: Definiowanie metody płatności odbiorcy
description: W tym artykule wyjaśniono, jak można utworzyć metodę płatności dla płatności odbiorcy.
author: ShivamPandey-msft
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f3843ce596d054263b69ccc577f3885970fe49d1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861510"
---
# <a name="establish-customer-method-of-payment"></a>Definiowanie metody płatności odbiorcy

[!include [banner](../../includes/banner.md)]

W tym artykule wyjaśniono, jak można utworzyć metodę płatności dla płatności odbiorcy. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. W okienku nawigacji przejdź do **Moduły > Rozrachunki z odbiorcami > Ustawienia płatności > Metody płatności**.
2. Wybierz pozycję **Nowy**.
3. W polu **Metody płatności** wprowadź identyfikator metody płatności. Metoda powiązana z identyfikatorem płatności jest wyświetlana na fakturach i w płatnościach, dlatego musi być na tyle opisowa, aby sugerować, jaki typ płatności jest rejestrowany i dla którego konta bankowego.  
4. W polu **Opis wprowadź** opis.
5. Wybierz, jaki stan płatności jest wymagany, aby można było księgować płatności. Podczas tworzenia płatności od odbiorcy można ją zaksięgować tylko wtedy, gdy stan płatności jest taki sam jak zdefiniowany tutaj.  
6. Określ, jak mają być tworzone płatności odbiorców za faktury. Ta opcja jest używana tylko przy generowaniu propozycji płatności. Można używać propozycji płatności dla płatności od odbiorców podczas operacji polecenia zapłaty, aby ściągać środki z rachunków bankowych odbiorców.  
7. Wybierz typ płatności. Typ płatności może pomóc określić, czy płatność będzie w jakikolwiek sposób weryfikowana.  
8. Wybierz typ konta, na jakim będą księgowane płatności. Zazwyczaj w tej opcji wybiera się opcję Bank.  
9. Wybierz konto bankowe, na którym ta płatność ma zostać zarejestrowana.
10. Wprowadź typ transakcji bankowej, aby zidentyfikować typu płatności używany przez bank. Typ transakcji bankowej jest używany w procesie uzgadniania konta bankowego i ułatwia uzgadnianie.  
11. Określ, czy ta płatności będzie tymczasowo księgowana na koncie pomostowym. Jeśli chcesz wypróbować określony czas obrotu kasowego dla rozliczania płatności przez bank, użyj funkcji transakcji pomostowej. Płatność tymczasowo zostanie zaksięgowana na koncie księgowym, dopóki bank jej nie rozliczy. Wtedy płatność zostanie przeniesiona na konto bankowe zdefiniowane w tym miejscu.  
12. Wprowadź konto główne używane dla księgowania pomostowego. To jest konto główne, na którym płatność zostanie tymczasowo zaksięgowana, jeśli są używane transakcje pomostowe.  
13. Na karcie **Format pliku** zdefiniuj ustawienia płatności elektronicznych.
14. Karta **Kontrola płatności** służy do definiowania pól, które są wymagane. Na przykład jeśli wszystkie płatności z tą metodą płatności mają być wpłacane, można zaznaczyć tę opcję na tej karcie.  
15. Karta **Atrybuty płatności** służy do określania, które atrybuty płatności mają być używane dla tej metody płatności.
16. Wybierz opcję **Zapisz**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
