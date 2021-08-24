---
title: Tworzenie i nabywanie środków trwałych z modułu Rozrachunki z dostawcami
description: Ten przewodnik po zadaniach zawiera instruktaż tworzenia i nabywania środka trwałego za pomocą procesu zakupów.
author: saraschi2
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 035fa86f0ff09faaa21c561cf7934455a6883cd8a7f917ac95bc7d096294d824
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743008"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Tworzenie i nabywanie środków trwałych z modułu Rozrachunki z dostawcami

[!include [banner](../../includes/banner.md)]

Ten przewodnik po zadaniach zawiera instruktaż tworzenia i nabywania środka trwałego za pomocą procesu zakupów.  Wykorzystuje role Księgowy i Pracownik ds. rozrachunków z dostawcami oraz firmę demonstracyjną USMF.


## <a name="set-fixed-assets-parameters"></a>Konfigurowanie parametrów środków trwałych
1. W **okienku nawigacji** przejdź do **Moduły > Środki trwałe > Ustawienia > Parametry środków trwałych**.
2. Rozwiń skróconą kartę **Zamówienia zakupu**.
3. Zaznacz pole wyboru **Zezwalaj na nabywanie środków trwałych z zakupów**.
4. Zaznacz pole wyboru **Utwórz środek trwały podczas księgowania dokumentu przyjęcia produktów lub faktury**.

## <a name="create-a-new-vendor-invoice"></a>Tworzenie nowej faktury od dostawcy
1. W **okienku nawigacji** przejdź do **Moduły > Rozrachunki z dostawcami > Obszary robocze > Wprowadzanie faktur od dostawcy**.
2. Kliknij przycisk **Nowa faktura od dostawcy**.
3. W polu **Konto płatnika** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu **Numer** wpisz wartość.
6. W polu **Data księgowania** wprowadź datę.
7. Kliknij przycisk **Dodaj wiersz.**
8. W polu **Numer towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie. Do nabywania środków trwałych mogą służyć towary niemagazynowe lub kategorie zaopatrzenia.  
9. Na liście kliknij łącze w wybranym wierszu.
10. W polu **Ilość** wpisz liczbę. Jeden wiersz faktury spowoduje utworzenie tylko jednego środka trwałego, niezależnie od ilości. Wartość pola ilości fakturowanej zostanie przeniesiona do ilości środka trwałego.  
11. W polu **Cena jednostkowa** wpisz liczbę.
12. Rozwiń skróconą kartę **Szczegóły wiersza**.
13. Kliknij kartę **Środki trwałe**.
14. Zaznacz pole wyboru **Utwórz nowy środek trwały**.
15. W polu **Grupa środków trwałych** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
16. Na liście wybierz grupę środków trwałych, która ma być używana podczas tworzenia nowego środka trwałego.
17. Na liście kliknij łącze w wybranym wierszu.
18. Kliknij przycisk **Księguj**. Środek trwały zostanie utworzony i nabyty podczas księgowania faktury.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]