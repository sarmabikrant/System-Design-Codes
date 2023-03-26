* Problem Description

	There is a store managing system. A store buys products and sells them.

	When buying a product, the Purchase ID is given with the product number, purchase price, and quantity.

	The product number is a value to distinguish products. With the same product number, purchase can be done several times.

	When cancelling a purchase, only the Purchase ID is given. Cancellation is possible only when all the quantity of the product that belongs to Purchase ID are left.

	When selling a product, the Sale ID is given with the product number, selling price, and quantity. Starting from the product that was bought the cheapest, sell the products. When the price is the same, sell the product whose value of Purchase ID is the smallest first.

	When refunding a product that was sold, only the Sale ID is given. All products that were sold with the Sale ID will be restocked.

	Implement each required function by referring to the following API description.

	The function signature below is based on C/C++. As for other languages, refer to the provided Main and User Code.

	The following is the description of API to be implemented.

	void init

		This function is called in the beginning of each test case. This function makes the store out of stock.

	int buy(int bld, int mProduct, int mPrice, int mQuantity)

		This function buys a quantity, mQuantity, of Product mProduct at a price of mPrice. The Purchase ID is bld.

		This function returns the total number of products of mProduct the store possesses after the purchase.

		Parameters

		bld: Purchase ID (1 bld ≤ 1,000,000,000)

		mProduct: Product number ( 1 ≤ mProducts 1,000,000,000)

		mPrice: Purchase price (1,000 mProduct ≤ 300,000)

		mQuantity: Purchase quantity (10mQuantity≤ 100)

		Returns

		Return the number of mProduct quantities in stock.

	int cancel(int bld)

		This function cancels the purchase whose Purchase ID is bld.

		Cancellation is possible only when all the quantity of the product purchased with bld is in stock. If even one is lacking, the cancellation fails and the function returns -1.

		Even if there was a time when the product bought with bid was sold, please note that cancellation is possible when all of it were restocked through refunds.

		When there is no purchase history through bld or the bid is already a cancelled Purchase ID, the cancellation fails and the function returns -1.

		When cancellation is possible, this function deletes the product that was bought through bid in stock and returns the number of the same products left in the store.

		Parameters

		bid: Purchase ID (1 ≤ bld ≤ 1,000,000,000)

		Returns

		If the cancellation fails, return -1.

		If the cancellation succeeds, return the number of products that are the same with the cancelled one left in the store.

	int sell (int sld, int mProduct, int mPrice, int mQuantity)

		This function sells a quantity, mQuantity, of Product mProduct at a price of mPrice. The Sale ID is sld. As Sale ID and Purchase ID are independent IDs, there are cases when the values of Sale ID and Purchase ID are the same with each other. When the quantity of mProduct in stock is less than mQuantity, selling fails and the function returns -1.

		When selling is possible, sell starting from the product that was bought the cheapest.

		When the price is the same, sell starting from the product whose Purchase ID is smaller than others. After selling, the function returns the total sales profit. The sales profit of each product is a value that subtracts the purchase price from the selling price.

		Parameters

		sid: Sale ID (1 ≤ sid≤ 1,000,000,000)

		mProduct: The product number ( 1 ≤ mProduct ≤ 1,000,000,000)

		mPrice: Selling price (2,000 mProduct ≤ 300,000) mQuantity: Selling quantity (1 ≤ mQuantity≤ 500)

		Returns

		If the selling fails, return -1.

		If the selling succeeds, return the total profit coming from selling sid.

	int refund(int sld)

		This function refunds a product that was sold through sld.

		This function returns the total number of products that was refunded. The returned products are all restocked.

		If there is no sale history through sld, or if it is already a Sale ID that was refunded, the refund fails and the function returns -1.

		Parameters
		sld: Sale ID (1 ≤ sld ≤ 1,000,000,000)

		Returns

		If the refund fails, return -1.

		If the refund succeeds, return the total number of refunded products.