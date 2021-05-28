---
title: Uruchom okresowe rozliczenie podatku potrąconego u źródła
description: W tym temacie opisano sposób rozliczania okresowego potrącenia podatku w źródle (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: cfab08a4190bf51518bd4a9b445b229a5081e87d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023497"
---
# <a name="run-the-periodic-tds-settlement-process"></a>Uruchom okresowe rozliczenie podatku potrąconego u źródła

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób rozliczania okresowego potrącenia podatku w źródle (TDS).

1. Przejdź do **Podatek \> Deklaracje \> Zaliczka na podatek \> Płatność zaliczki na podatek**.

    [![Okno dialogowe płatności podatku u źródła](./media/apac-ind-TDS-47.png)](./media/apac-ind-TDS-47.png)

2. W oknie dialogowym **Płatność potrąconej zaliczki** na podatek w polu **Typ podatku** wybierz opcję **TDS**.
3. W polu **Numer konta podatkowego (TAN)** wybierz numer konta podatkowego, dla których ma być uruchomiony proces rozliczania.
4. W polu **Grupa składników** potrąconej zaliczki na podatek wybierz grupę składników TDS, dla której ma być uruchomiony proces rozliczania.
5. W polu **Okres rozliczenia** wybierz okres rozliczenia TDS, dla których ma być uruchomiony proces rozliczania.

    > [!NOTE]
    > Proces rozliczania TDS jest uruchamiany dla wszystkich okresów, które są ustawione dla okresu rozliczeniowego TDS na karcie **Okresy** na stronie **Okresy rozliczenia potrąconej zaliczki** na podatek (**Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Okresy rozliczenia potrąconych zaliczek na podatek**).

6. W polu **Od dnia** wybierz datę rozpoczęcia, od których ma być uruchomiony proces rozliczania TDS.

    W przypadku określonego okresu w okresie rozliczeniowym data rozpoczęcia zdefiniowana dla tego okresu jest datą „od”. Na przykład okres rozliczeniowy TDS ma dwa okresy: od 1 kwietnia do 30 kwietnia 2009 oraz od 1 maja do 31 maja 2009. W przypadku wybrania daty rozpoczęcia **2009-04-06** (6 kwietnia 2009) jako daty rozpoczęcia w polu **Od dnia** proces rozliczania będzie nadal uruchamiany od 1 kwietnia 2009.

    W przypadku wprowadzenia późniejszego okresu w polu **Od dnia** bez rozliczania poprzedniego okresu w okresie rozliczeniowym rozliczenie nie będzie występować w żadnym z poprzednich okresów. Na przykład okres rozliczeniowy TDS ma trzy okresy: od 1 kwietnia do 30 kwietnia 2009, 1 maja do 31 maja 2009 oraz od 1 czerwca do 30 czerwca 2009. W przypadku wybrania daty rozpoczęcia **2009-05-01** (1 maja 2009) jako daty rozpoczęcia w polu **Od dnia** proces rozliczania będzie uruchamiany tylko od 1 maja do 31 maja 2009. Rozliczenie nie nastąpi za okres od 1 kwietnia do 30 kwietnia 2009.

7. W polu **Data transakcji** należy wybrać datę zaksięgowania transakcji rozliczenia podatku potrącanego u źródła.
8. W oknie dialogowym **Wersja Płatność potrąconej zaliczki na podatek** wybierz wersję rozliczenia TDS:

     - **Oryginał** — ta opcja służy do pierwszego uruchomienia procesu rozliczania TDS. Oryginalna wersja płatności jest używana tylko raz do uruchomienia procesu rozliczenia podatku u źródła dla kombinacji numeru TAN, grupy składnika podatku u źródła oraz okresu rozliczenia podatku u źródła.
    - **Najnowsze wersje** — tej opcji należy użyć, jeśli proces rozliczania TDS został już uruchomiony w określonym okresie. Uwzględnij transakcje z datami wstecz, które zostały zaksięgowane po wcześniejszym uruchomieniu procesu rozliczania dla okresu. Za pomocą tej opcji można uruchamiać proces rozliczania dowolną liczbę razy.

9. Zaznacz pole wyboru **Aktualizuj**, aby uruchomić proces rozliczania TDS i zaksiągować kwoty na kontach księgowych. Jeśli to pole wyboru jest wyczyszone, proces rozliczania nie będzie uruchamiany i wpisy finansowe nie będą generowane.
10. Wybierz **przycisk OK**, aby uruchomić proces rozliczania TDS i wygenerować raport płatności potrąconej zaliczki na podatek. Stan transakcji TDS uwzględnionych w procesie rozliczania jest pokazywany jako **Rozliczone** na stronie **Rozliczenie** (przejdź do **Rozrachunki z dostawcami \> Płatności \> Arkusz płatności dostawców**, wybierz **Wiersze**, wybierz **Funkcje** a następnie wybierz opcję **Rozliczenie**).

### <a name="important-points"></a>Ważne punkty

- Jeśli w procesie rozliczenia nie zostanie wybrana grupa składnika podatku u źródła, rozliczenie nastąpi dla wszystkich grup składników podatku u źródła dla wybranego TAN i okresu rozliczeniowego. Dla każdej grupy składników potrąconej zaliczki na podatek na stronie edycji **otwartej transakcji** tworzony jest osobny wiersz.
- Proces rozliczania opiera się na charakterze kategorii oceny dla okresu rozliczeniowego. Transakcje, których charakter kategorii oceny to **Firma**, są rozliczane i pokazywane w jednym wierszu na stronie **edycji otwartej transakcji**. Transakcje, których charakter kategorii oceny to coś innego niż **Firma**, są rozliczane i pokazywane w jednym wierszu na stronie **edycji otwartej transakcji**.
- Data płatności dla rozliczonych wierszy transakcji TDS na stronie edycji **otwartej transakcji** jest oparta na warunkach płatności, które zdefiniowano dla dostawcy urzędu TDS na **stronie Dostawcy**. Jeśli warunki płatności nie są zdefiniowane dla dostawcy urzędu TDS, ostatni dzień okresu rozliczeniowego jest wyświetlany jako termin.
