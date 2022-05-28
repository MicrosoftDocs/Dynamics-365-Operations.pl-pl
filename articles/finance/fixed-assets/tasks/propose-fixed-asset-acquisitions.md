---
title: Proponowanie nabycia środka trwałego
description: W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych.
author: moaamer
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd54642e5ec6c56fbc3a5ebb07fc8fdaf5545926
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725688"
---
# <a name="propose-fixed-asset-acquisitions"></a>Proponowanie nabycia środka trwałego

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób nabywania środka trwałego przy użyciu propozycji nabycia zdefiniowanej w arkuszu środków trwałych. Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF. Aby nabyć środek trwały za pośrednictwem arkusza propozycji środków trwałych, należy najpierw utworzyć rekord środka trwałego, a następnie zdefiniować cenę nabycia w księdze składników majątku.

## <a name="create-an-asset-acquisition-proposal"></a>Tworzenie propozycji nabycia składnika majątku

Aby utworzyć propozycję nabycia składnika majątku, należy wykonać następujące kroki. 

1. W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** wprowadź lub wybierz wartość.
4. W okienku akcji wybierz **Wiersze**.
5. Wybierz **Propozycje**.
6. Wybierz **Propozycja nabycia**.
7. Wybierz **Filtry**. Wybierz **Resetuj**, aby wyczyścić poprzednie wartości.
8. Zaznacz wiersz **Numer środka trwałego**.
9. W polu **Kryteria** wprowadź lub wybierz wartość. Skonfiguruj pozostałe kryteria środków trwałych, które chcesz nabyć za pomocą tej propozycji.  
10. Wybierz dwa razy **OK**, aby wyjść z okienka.
- Sprawdź, czy są utworzone wiersze transakcji.  
- W propozycji nabycia zostaną uwzględnione tylko środki trwałe, które w księdze mają ustawioną datę nabycia i cenę nabycia.  
11. Na stronie wybierz kartę **Księgi**.
12. Wybierz opcję **Zaksięguj**.

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>Uwzględnij domyślne wymiary finansowe w propozycji nabycia

Transakcję nabycia można utworzyć za pomocą dodatków programu Excel, przechodząc do pozycji **Składniki majątku > Wpisy w arkuszu > Arkusz składników majątku**. Utwórz nowy arkusz i przenieś do sekcji **Wiersze** na stronie, wybierz ikonę programu Excel, a następnie wybierz wiersz arkusza składników majątku. System utworzy i otworzy szablon programu Excel reprezentujący wiersze arkusza. Można dodać dane do wierszy arkusza, które dodajesz do szablonu, a następnie opublikować je z powrotem w systemie. 

Jeśli dla wybranej księgi składników majątku zostały ustawione wymiary domyślne oraz odpowiednie składniki majątku wprowadzone w szablonie programu Excel, domyślne wymiary finansowe będą wywoływane z danych główne księgi składników majątku, gdy arkusz zostanie opublikowany w programie Excel w systemie. Aby podczas publikowania arkusza składników majątku w dodatku programu Excel automatycznie uwzględniać wymiary finansowe w księdze składników majątku, należy wcześniej skonfigurować wymiary domyślne.  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
