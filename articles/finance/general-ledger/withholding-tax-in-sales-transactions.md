---
title: Zaliczka na podatek w transakcjach sprzedaży
description: W tym temacie wymieniono kroki uniknięcia obliczania potrąconej zaliczki na podatek dla wybranych odbiorców. W przypadku odbiorców, którzy określą potrąconą zaliczkę na podatek w płatnościach na rzecz użytkownika, można przypisać domyślną grupę potrąconej zaliczki na podatek.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: b221fc04ef82f148846fc0c282f6c8601f0eb4759d99a8dee02256cc0d42417f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747090"
---
# <a name="withholding-tax-in-sales-transactions"></a>Zaliczka na podatek w transakcjach sprzedaży

W tym temacie wymieniono kroki uniknięcia obliczania potrąconej zaliczki na podatek dla wybranych odbiorców. W przypadku odbiorców, którzy określą potrąconą zaliczkę na podatek w płatnościach na rzecz użytkownika, można przypisać **Domyślną grupę potrąconej zaliczki na podatek** na stronie **Klienci**. 

1. Przejdź do **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy**.

2. Kliknij odpowiednie konto odbiorcy i kliknij przycisk **Edytuj**.

3. Na karcie **Faktura i dostawa** w polu **Oblicz potrącanie zaliczki na podatek** ustaw wartość **Tak**.

   > [!NOTE] 
   > Podatek u źródła nie zostanie obliczony, jeśli **Obliczanie zaliczki na podatek** nie jest włączone dla tego odbiorcy w danych podstawowych.

4. Wybierz grupę Potrącona zaliczka na podatek na liście **Grupa potrąconej zaliczki na podatek**.

5. Kliknij przycisk **Zapisz**.

W przypadku towarów / usług, które podlegają potrąceniu u źródła, można przypisać domyślną **Grupę podatku potrącanego u źródła** w obszarze **Zwolnione produkty**.

1. Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.

2. Kliknij odpowiedni numer pozycji i kliknij przycisk **Edytuj**.

3. Na karcie **Sprzedaż** kliknij przycisk **Oblicz potrącenie zaliczki na podatek**.

   > [!NOTE] 
   > Potrącona zaliczka na podatek nie zostanie obliczona, jeśli ustawienie **Oblicz potrąconej zaliczki na podatek** nie ma wartości **Tak** dla tej pozycji na karcie **Sprzedaż** na stronie **Zwolniony produkt**.

4. Wybierz grupę Potrącona zaliczka na podatek od pozycji na liście **Grupa potrąconej zaliczki na podatek od pozycji**.

5. Kliknij przycisk **Zapisz**.

Za pomocą strony **Zamówienia sprzedaży** można przypisać grupy potrąconych zaliczek na podatek i grupy potrąconych zaliczek na podatek od pozycji. 

Podczas tworzenia nowego zamówienia sprzedaży jako domyślne wpisy w wierszach zamówienia sprzedaży będą używane domyślna grupa potrąconej zaliczki na podatek i grupa potrąconej zaliczki na podatek od pozycji.

Potrącona zaliczka na podatek jest obliczana i księgowana za pomocą **Arkusza płatności odbiorcy**. Można ręcznie skorygować stosowany kod potrąconej zaliczki na podatek oraz rzeczywistą kwotę potrąconej zaliczki na podatek na karcie **Potrącona zaliczka na podatek** na stronie **Rozlicz transakcje**.

Obliczona kwota potrąconej zaliczki na podatek zostanie potrącona z płatności odbiorcy i zaksięgowana na koncie **Potrąconej zaliczki na podatek** w powiązanym załączniku.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]