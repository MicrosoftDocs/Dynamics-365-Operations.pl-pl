---
title: Korygowanie wynajmów
description: W temacie wyjaśniono sposób korygowania wynajmu. Korekta może być wymagana w przypadku zmodyfikowania warunków wynajmu, wydłużenia wynajmu lub zmiany innych okoliczności.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c6e20e72fb2816c32e71e8921a94724ae5656
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447011"
---
# <a name="adjust-leases"></a>Korygowanie wynajmów

[!include [banner](../includes/banner.md)]

W temacie wyjaśniono sposób korygowania wynajmu. Korekta może być wymagana w przypadku zmodyfikowania warunków wynajmu, wydłużenia wynajmu lub zmiany innych okoliczności. Wynajem składników majątku jest zgodny z przepisami Accounting Standards Codification Topic 842 (ASC 842) i International Financial Reporting Standard 16 (IFRS 16) dotyczącymi korekt wynajmów. ASC 842-20-15-1 definiuje modyfikację wynajmu jako dowolną zmianę postanowień umowy, która powoduje zmianę zakresu wynajmu lub uwag do niego. Akapit 39 IFRS 16 wskazuje, że najemca musi zmienić wartość zobowiązania z tytułu wynajmu, tak aby odzwierciedlała ona zmiany w opłatach z tytułu wynajmu.

W przypadku organizacji, które stosują się do ASC 842 lub IFRS 16, wynajem jest zmieniany w celu odzwierciedlenia zmiany bieżącej wartości przyszłych opłat z tytułu wynajmu (PVFMLP). Jeśli PVFMLP wzrośnie, utworzony wpis w arkuszu dla różnicy między nowym PVFMLP a poprzednim PVFMLP będzie debetowy w składniku majątku z PDU i kredytowy w zobowiązaniu z tytułu wynajmu. Jeśli PVFMLP zmniejszy się, wpis w arkuszu dla tej różnicy będzie debetowy w zobowiązaniu z tytułu wynajmu oraz kredytowy w składniku majątku z PDU.

Jeśli korekta spowoduje obniżenie wartości składnika majątku z PDU poniżej 0 (zera), reszta zostanie zaksięgowana po stronie kredytowej na koncie księgowania modyfikacji zysku z wynajmu, który jest określony na stronie **Konta księgowania wynajmów**. Konta systemowe dla tych transakcji i innych wpisów korekty, takich jak zmiany klasyfikacji, początkowe koszty bezpośrednie, prowizje stymulujące wynajem, przedpłaty czy koszty demontażu powstające w wyniku modyfikacji wynajmu.

Aby uzyskać szczegółowe wskazówki dotyczące transakcji korekty wynajmu, zaleca się zapoznanie się z IFRS 16 i ASC 842.

Aby skorygować wynajem, wykonaj następujące kroki. Zmodyfikowane dane spowodują aktualizację harmonogramów wynajmów po uruchomieniu procesu tworzenia harmonogramu.

1. Przejdź do **Wynajem składnika majątku \> Wynajmy \> Podsumowanie wynajmu**.
2. Na stronie **Podsumowanie wynajmu** wybierz wynajem, który chcesz skorygować, a następnie wybierz opcję **Koryguj wynajem**.
3. Na stronie **Koryguj wynajem** wprowadź nowe informacje dotyczące korygowanego wynajmu.

    Zauważ, że strona **Koryguj wynajem** jest podobna do strony **Dodaj wynajem**. Data rozpoczęcia określona podczas dodawania wynajmu określa, kiedy rozpoczyna się nowy wynajem. Podobnie pole **Data modyfikacji** na stronie **Koryguj wynajem** określa datę rozpoczęcia wynajmu po korekcie. Data ta nie może być późniejsza niż data rozpoczęcia w wierszach harmonogramu płatności.

    > [!NOTE]
    > Pola **Uwagi dotyczące PDU** dotyczą korekty wynajmu. Jeśli ze zmodyfikowanym wynajmem nie są powiązane koszty bezpośrednie, prowizje stymulujące wynajem, przedpłaty lub koszty demontażu, należy pozostawić te pola puste. Oryginalne kwoty nie będą stosowane do zaktualizowanego wynajmu. Wszelkie dodatkowe koszty poniesione w momencie modyfikacji wynajmu należy wprowadzić na stronie **Koryguj wynajem**.
    > 
    > Na przykład najmodawca oferuje 1000 dolarów prowizji stymulującej wynajem za przedłużenie wynajmu. W takim przypadku podczas korygowania wynajmu, aby uwzględnić to przedłużenie, wprowadź **1000** w polu **Prowizje stymulujące wynajem**. Jeśli żadne prowizje nie są skojarzone z korektą wynajmu, należy wyczyścić wszystkie wartości wprowadzone wcześniej w tym polu. Ta sama logika jest stosowana do innych uwag dotyczących PDU.

    Wiersze harmonogramu płatności dla skorygowanego wynajmu należy tworzyć prospektywnie. Wiersze harmonogramu płatności, które są tworzone prospektywnie, nie mogą się rozpocząć przed wejściem w życie korekty wynajmu.

    Poniższe kroki są niemal identyczne z krokami dotyczącymi wstępnego rozpoznawania wynajmu.

4. Wybierz opcję **Utwórz harmonogramy**, aby wygenerować skorygowany harmonogram płatności. Zostanie wyświetlony komunikat informujący o tym, że utworzono harmonogram płatności dla tego wynajmu.

    > [!IMPORTANT]
    > Przed wybraniem opcji **Utwórz harmonogramy** należy się upewnić, że data modyfikacji i wiersze harmonogramu płatności są właściwe. Upewnij się również, że wszystkie początkowe koszty bezpośrednie, prowizje stymulujące wynajem, przedpłaty lub koszty demontażu odpowiadają wyłącznie kosztom wynikającym z korekty.

5. Aby wyświetlić nowo utworzony harmonogram płatności, wybierz opcję **Księgi** i otwórz stronę **Harmonogram płatności**.
6. Na stronie **Harmonogram płatności** można edytować skorygowane kwoty płatności przed potwierdzeniem harmonogramu płatności. Aby potwierdzić harmonogram, wybierz opcję **Potwierdź harmonogram**.

    Po potwierdzeniu harmonogramu płatności zostaną utworzone nowe harmonogramy amortyzacji środków trwałych i zobowiązań z tytułu leasingu finansowego.

7. Aby wyświetlić nowy harmonogram zobowiązań z tytułu leasingu finansowego generowany na podstawie nowych danych wejściowych, zamknij stronę **Harmonogram płatności** i otwórz stronę **Harmonogram amortyzacji zobowiązań**.
8. Aby wyświetlić nowo wygenerowany harmonogram amortyzacji środków trwałych, otwórz stronę **Harmonogram amortyzacji składników majątku** na stronie **Szczegóły księgi**.
9. Aby wygenerować wpis w arkuszu dotyczący korekty, wybierz **Funkcja \> Korekta wynajmu**. Zostanie wyświetlony komunikat informujący o utworzeniu wpisu w arkuszu dotyczącego korekty. 
10. Aby wyświetlić wpis w arkuszu, należy wybrać **Arkusze \> Arkusz wynajmu składnika majątku**.
11. Aby zaksięgować wpis w arkuszu, wybierz wiersz, a następnie wybierz pozycję **Zaksięguj**.

## <a name="view-lease-versions"></a>Przeglądanie wersji wynajmu

Jeśli wynajem został zmodyfikowany, można wyświetlić jego różne wersje. Można również wyświetlić harmonogramy historyczne i szczegóły dotyczące przeszłych wynajmów.

1. Na stronie **Podsumowanie wynajmu** wybierz wynajem do skopiowania, a następnie w okienku akcji wybierz opcję **Historia wersji wynajmu**.

    Jeśli wybrany wynajem został skorygowany, na stronie **Historia wersji wynajmu** zostaną wyświetlone jego różne wersje. Pierwotny wynajem jest oznaczony jako **1**, a kolejne wersje mają rosnącą kolejność liczbową.

    W przypadku wybranej wersji wynajmu można wyświetlić wymiary finansowe, szczegóły umowy, lokalizację i wiersze harmonogramu płatności.

2. Aby wyświetlić harmonogramy historyczne, otwórz zmodyfikowany wynajem na stronie **Podsumowanie wynajmu**, wybierz żądaną księgę, a następnie w okienku akcji wybierz opcję **Historia wersji księgi**.
3. Na stronie **Wersja księgi** wybierz żądaną wersję i żądany harmonogram do wyświetlenia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]