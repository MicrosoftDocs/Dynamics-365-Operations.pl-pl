---
title: Otwieranie szablonów arkuszy finansowych w pakiecie Office
description: W tym temacie opisano problemy, które mogą wystąpić podczas tworzenia niestandardowych arkuszy finansowych przy użyciu szablonu programu Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0773f47551b2460ec310b92b67c634b433147749
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/24/2021
ms.locfileid: "6089464"
---
# <a name="open-financial-journal-templates-in-office"></a><span data-ttu-id="9015c-103">Otwieranie szablonów arkuszy finansowych w pakiecie Office</span><span class="sxs-lookup"><span data-stu-id="9015c-103">Open financial journal templates in Office</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9015c-104">W tym temacie opisano problemy, które mogą wystąpić podczas tworzenia niestandardowych arkuszy finansowych przy użyciu szablonu programu Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="9015c-104">This topic describes issues that might occur when you create custom financial journals by using a Microsoft Excel template.</span></span>

## <a name="symptom"></a><span data-ttu-id="9015c-105">Objaw</span><span class="sxs-lookup"><span data-stu-id="9015c-105">Symptom</span></span>

<span data-ttu-id="9015c-106">Utworzono niestandardowy szablon programu Excel dla arkuszy finansowych, ale nie jest on wyświetlany w menu **Otwórz wiersze w programie Excel**.</span><span class="sxs-lookup"><span data-stu-id="9015c-106">You created a custom Excel template for financial journals, but it doesn't appear on the **Open lines in Excel** menu.</span></span> <span data-ttu-id="9015c-107">Może on także być widoczny w menu, jednak po jego wybraniu otwiera się inny szablon.</span><span class="sxs-lookup"><span data-stu-id="9015c-107">Alternatively, it does appear on the menu, a different template is opened but when you select it.</span></span>

## <a name="resolution"></a><span data-ttu-id="9015c-108">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="9015c-108">Resolution</span></span>

<span data-ttu-id="9015c-109">Domyślna funkcja otwierania w programie Excel używa głównego źródła danych (tabeli) bieżącej strony w celu określenia, które szablony lub jednostki danych pakietu Office mają być wyświetlane jako opcje w menu **Otwórz w programie Excel**.</span><span class="sxs-lookup"><span data-stu-id="9015c-109">The default Open in Excel functionality uses the root data source (table) of the current page to determine which Office templates or data entities appear as options on the **Open in Excel** menu.</span></span> <span data-ttu-id="9015c-110">Takie zachowanie programu nie sprawdza się idealnie w przypadku arkuszy finansowych, ponieważ arkusze finansowe używają tych samych tabel (LedgerJournalTable i LedgerJournalTrans), które są głównym źródłem danych wielu innych typów arkuszy.</span><span class="sxs-lookup"><span data-stu-id="9015c-110">This behavior isn't an ideal experience for financial journals, because financial journals use the same tables (LedgerJournalTable and LedgerJournalTrans) as the root data source of many other types of journals.</span></span>

<span data-ttu-id="9015c-111">W przypadku arkuszy finansowych funkcja Otwórz wiersze w programie Excel ma na celu wyświetlanie szablonów, które zostały zaprojektowane z myślą o rodzaju arkusza, z którym aktualnie pracujesz, takim jak arkusz finansowy lub arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="9015c-111">For financial journals, the Open Lines in Excel functionality is intended to show templates that are designed for the journal that you're currently working in the context of, such as the general journal or a payment journal.</span></span> <span data-ttu-id="9015c-112">Na przykład szablon, który jest przeznaczony do użytku z arkuszem płatności dostawcy, będzie zaprojektowany tak, by wymusić wybór Twojego głównego konta jako konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="9015c-112">For example, a template that is intended to be used with a vendor payment journal will be designed to enforce your primary account as a vendor account.</span></span>

<span data-ttu-id="9015c-113">Jeśli chcesz podwyższyć poziom szablonu tak, aby był on dostępny w menu **Otwórz wiersze w programie Excel** i **Otwórz w programie Excel**, najłatwiej będzie zaimplementować interfejs **LedgerIJournalExcelTemplate** i rozszerzyć klasę **DocuTemplateRegistrationBase**.</span><span class="sxs-lookup"><span data-stu-id="9015c-113">If you want to promote a template so that it's available on the **Open lines in Excel** and **Open in Excel** menus, an easy developer experience is to implement the **LedgerIJournalExcelTemplate** interface and extend the **DocuTemplateRegistrationBase** class.</span></span> <span data-ttu-id="9015c-114">W systemie można się spotkać z wieloma zaimplementowanymi przykładami takiego podejścia.</span><span class="sxs-lookup"><span data-stu-id="9015c-114">Many examples of this approach are implemented in the system.</span></span> <span data-ttu-id="9015c-115">Jednym z przykładów, którego można użyć na potrzeby odwołania, jest interfejs **LedgerDailyJournalExcelTemplate** utworzony dla arkusza finansowego (lub arkusza dziennego).</span><span class="sxs-lookup"><span data-stu-id="9015c-115">One example that can be used for reference is the **LedgerDailyJournalExcelTemplate** interface that was created for the general journal (or daily journal).</span></span>

<span data-ttu-id="9015c-116">Gdy dla szablonu zostanie zaimplementowany interfejs **LedgerIJournalExcelTemplate**, w menu **Otwórz wiersze w programie Excel** szablony będą filtrowane według typu arkusza i będą wyświetlane tylko szablony dostępne dla danego arkusza.</span><span class="sxs-lookup"><span data-stu-id="9015c-116">When the **LedgerIJournalExcelTemplate** interface is implemented for your template, the **Open Lines in Excel** menu will filter templates by the journal type of your journal and will show only the templates that are available for that journal.</span></span> <span data-ttu-id="9015c-117">Interfejs zapewnia również metodę weryfikacji, która gwarantuje, że nie można otworzyć dla arkusza szablonu, jeśli nie spełnia on wymagań dotyczących typu konta.</span><span class="sxs-lookup"><span data-stu-id="9015c-117">The interface also provides a validation method that ensures that a template can't be opened for a journal if it doesn't meet the account type requirements.</span></span> <span data-ttu-id="9015c-118">Można na przykład określić typ konta **Dostawca** lub **Księga**.</span><span class="sxs-lookup"><span data-stu-id="9015c-118">For example, you can specify that the account type must be of the **Vendor** or **Ledger** type.</span></span>

<span data-ttu-id="9015c-119">Aby uzyskać więcej informacji o tej funkcji, patrz temat [Dodawanie szablonów do menu Otwórz wiersze w programie Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span><span class="sxs-lookup"><span data-stu-id="9015c-119">For more information about this functionality, see [Add templates to the Open lines in Excel menu](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span></span>
