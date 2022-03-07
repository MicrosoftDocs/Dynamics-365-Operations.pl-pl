---
title: Tworzenia kodów opłat
description: W tym temacie opisano sposób konfigurowania kodów opłat zarówno dla rozrachunków z dostawcami, jak i rozrachunków z odbiorcami.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MarkupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 034be190890a67fd0921d40fffdc704b9d6d5df7
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014077"
---
# <a name="create-charges-codes"></a>Tworzenia kodów opłat

W tym temacie opisano sposób konfigurowania kodów opłat zarówno dla rozrachunków z dostawcami, jak i rozrachunków z odbiorcami. Jeśli organizacja wymaga, aby oprócz towarów w zamówieniu sprzedaży lub zamówieniu zakupu kwoty sprzedaży lub zakupu było śledzone, można do tego celu użyć kodów opłat. Na przykład opłaty frachtowe i ubezpieczenie są opłacane w zamówieniu zakupu i kwoty te są oddzielnie pozycjami w zamówieniu zakupu. W tym przypadku można określić, czy kwoty są księgowane na kontach wydatków czy dodawane do kosztu towarów.

## <a name="set-up-charges-codes-for-accounts-receivable"></a>Ustaw kody opłat dla rozrachunków z odbiorcami

Aby utworzyć kody opłat dla rozrachunków z odbiorcami, wykonaj następujące czynności.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia opłat** &gt; **Kod opłat**.
2. Wybierz pozycję **Nowy**.
3. W polu **Kod opłat** wpisz kod opłaty.
3. W polu **Opis** wprowadź opis opłaty.
4. Opcjonalnie: w polu **Grupa podatków dla pozycji** wybierz grupę podatków.
5. Na skróconej karcie **księgowania** określ sposób automatycznego księgowania opłaty po stronie debetowej i kredytowej.
6. Jeśli jako typ debetu lub kredytu wybrano **konto księgowe**, określ typ księgowania w polach **Księgowanie** i określ konto główne w polach **Konto**.

### <a name="example"></a>Przykład

Odbiorca płaci opłatę. W związku z tym jest on dodawany do sum zamówienia sprzedaży. Ustawiasz następujące informacje o publikacji:

- W polu **Typ** w sekcji **Debet** wybierz pozycję **Odbiorca/Dostawca**, aby dodać opłatę fakturową do konta odbiorcy.
- W polu **Typ** w sekcji **Kredyt** wybierz opcję **Konto księgowe**. Następnie w polu **Konto** wybierz konto główne dla przychodów z opłat za faktury.

> [!NOTE]
> Jeśli typ obciążenia lub kredytu dla wybranego kodu to **Konto księgi** lub **Pozycja**, możesz wprowadzić inną walutę dla transakcji obciążenia.

Tekst opłat można wydrukować w języku przypisanym do klienta. Aby określić tekst kodu opłat w innych językach, wybierz **polecenie Tłumaczenia**.

## <a name="set-up-charges-codes-for-accounts-payable"></a>Ustaw kody opłat dla rozrachunków z dostawcami

Aby utworzyć kody opłat dla rozrachunków z dostawcami, wykonaj następujące czynności.

1. Wykonaj jeden z następujących kroków:

    - Wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Ustawienia** **opłat** &gt; **Kod opłat**.
    - Przejdź do **Zaopatrzenie i sourcing** &gt; **Ustawienia** &gt; **Opłaty** &gt; **Kod opłat**.

2. Wybierz pozycję **Nowy**.
3. W polu **Kod opłat** wpisz kod opłaty.
3. W polu **Opis** wprowadź opis opłaty.
4. Opcjonalnie: w polu **Grupa podatków dla pozycji** wybierz grupę podatków.
5. Opcjonalne: W polu **Maksymalną ilość** wprowadź maksymalną kwotę dozwoloną dla kodu opłat.

    To pole służy do sprawdzania poprawności opłat dla faktur od dostawców. Aby włączyć weryfikację opłat, zaznacz pole wyboru **Włącz weryfikację uzgadniania faktur** na karcie **Weryfikacja faktury** na stronie **Parametry rozrachunków z dostawcami**.

    > [!IMPORTANT]
    > Aby sprawdzić poprawność opłat dla faktur, należy również utworzyć wystąpienie typu reguły, które jest oparte na opłatach dla określonych zasad faktury od dostawcy.

6. Na skróconej karcie **księgowania** określ sposób automatycznego księgowania opłaty po stronie debetowej i kredytowej.
7. Jeśli jako typ obciążenia lub uznania wybrałeś **Konto księgi**, określ typ księgowania w polach **Księgowanie debetowe** i **Księgowanie kredytowe** oraz określ konto główne w **Rachunek debetowy** i **Rachunek kredytowy** pól.
8. Aby włączyć porównanie wartości opłat dla faktury zawierającej opłaty z odpowiedniego nagłówka lub wierszy zamówienia zakupu, zaznacz pole wyboru **Porównaj wartości zamówienia zakupu i faktury**.

### <a name="example"></a>Przykład

Opłatę można rejestrować jako wydatek jako część sumy zamówienia zakupu lub faktury dostawcy. Wykonaj poniższe czynności, aby skonfigurować informacje o publikowaniu. 

- W polu **Typ** w sekcji **Kredyt** wybierz pozycję **Odbiorca/Dostawca**, aby dodać opłatę fakturową do konta dostawcy.
- W polu **Typ** w sekcji **Debet** wybierz opcję **Konto księgowe**. Następnie w polu **Konto** wybierz konto główne dla wydatków z opłat za faktury.

Wykonaj poniższe czynności, aby skonfigurować informacje o księgowaniu, tak aby opłata jednostkowa była dodawana do kosztu towaru.

- W polu **Typ** w sekcji **Kredyt** wybierz pozycję **Odbiorca/Dostawca**, aby dodać opłatę fakturową do konta dostawcy.
- W polu **Typ** w sekcji **Debet** wybierz pozycję **Towar**, aby dodać opłatę do kosztu towaru.

> [!NOTE]
> Może być wskazane użycie waluty innej niż określona w zamówieniu zakupu lub fakturze. Możesz wpisać inną walutę, jeśli typem debetu lub kredytu dla wybranego kodu opłat jest **Konto księgowe** lub **Towar**.

Tekst opłat można wydrukować w języku przypisanym do klienta. Aby określić tekst kodu opłat w innych językach, wybierz **polecenie Tłumaczenia**.
