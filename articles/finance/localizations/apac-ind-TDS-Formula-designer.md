---
title: Projektant formuł dla obliczeń TDS
description: Ten temat zawiera przykład obliczania podatku potrąconego w źródle (TDS) na podstawie formuły zdefiniowanej dla każdego kodu podatku TDS w grupie TDS dołączonej do transakcji.
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3d8e098243688ebf6977db97130592443e269973
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408128"
---
# <a name="formula-designer-for-tds-calculations"></a>Projektant formuł dla obliczeń TDS

[!include [banner](../includes/banner.md)]

W tym temacie popisano przykład obliczania podatku potrąconego w źródle (TDS) na podstawie formuły zdefiniowanej dla każdego kodu podatku TDS. Kody podatków TDS są definiowane w grupie TDS dołączonej do transakcji. Przed zaprojektowanie formuł TDS należy wykonać podstawowe ustawienia wymagane dla identyfikatorów TDS, tak jak podano w poniższych krokach. 

- Skonfiguruj grupy składników TDS za pomocą strony **Grupy potrąconych zaliczek na podatek**. 
- Skonfiguruj składniki TDS i dołącz do składników TDS grupę składników TDS, korzystając ze strony **Składników potrąconej zaliczki na podatek**. 
- Skonfiguruj kody podatku TDS i dołącz składniki TDS do kodów podatków, korzystając ze strony **Kody potrąconej zaliczki na podatek**. 
- Skonfiguruj grupy TDS za pomocą strony **Grupy potrąconych zaliczek na podatek**. Następnie należy dołączyć kody podatków TDS do grupy podatków i zdefiniować formułę na stronie **Projektant formuł**. 

**Przykładowa formuła**

W tym przykładzie grupa TDS Rent jest dołączona do faktury zakupu utworzonej dla dostawcy A. Kwota faktury wynosi 100 000 USD. Zapoznaj się z poniższą tabelą, aby wyświetlić obliczenia TDS dla faktury.

| Grupa TDS                                                   | Kody podatków TDS dołączone do grupy TDS | Wartość              | Podstawa opodatkowania (projektant formuł) | Obliczanie wyrażenia (Projektant formuł) | Kwota podstawowa | Obliczona kwota podatku TDS |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| Dzierżawa                                                         | TDS  (TDS składnik-TDS)                | 10%                | Kwota brutto                      |                                            | 100,000      | 10,000                 |
| Dopłata (składnik TDS — dopłata)                         | 10%                                     | Wył. kwota brutto | +TDS                              |                   10000                    | 1 000        |                       |
| Pe-Cess (składnik TDS — Pe-Cess)                            | 2%                                      | Wył. kwota brutto | +TDS+Dopłata                    |                   11000                    | 220         |                       |
| SHE Cess (składnik TDS — SHE Cess)                          | 1%                                      | Wył. kwota brutto | +TDS+Dopłata                    |                   11000                    | 110         |                       |
| **Łączny** **identyfikator TDS** **obliczony** **dla** **faktury** | **11,330**                               |                    |                                   |                                            |             |                       |

Wpisy załącznika są tworzone w następujący sposób.

| Konto           | Uznanie  | Środki |
| ----------------- | ------ | ------ |
| Dzierżawa              | 100,000 |        |
| Dostawca A          |        | 100,000 |
| Dostawca A          | 11,330  |        |
| TDS do zapłacenia       |        | 10,000  |
| Dopłata należna |        | 1 000   |
| PE-Cess do zapłaty   |        | 220    |
| SHE-Cess do zapłaty  |        | 110    |
