The code implements a feature that quickly finds a hotel room which a customer wants.

N, the number of hotels registered in the system is 1,000 at most.
The values of Hotel IDs are between 1 and N. The values are different from one another.

Each hotel has 100 rooms at most.
The ID value of each Room is between 1 and 100,000. The given values are different from one another.


Each room has the following information.

Region: 	1-10
Number of Beds: 2-10
Room Type:	1-4
View Type:	1-4
Initial Price:  10,000-20,000

The hotel search service returns the cheapest room among the rooms that match the filter options selected.

The information the customer entered is as below.

Check-in Date:    1 - 9,999
Check-out Date:   Check-in Date +1 ~ 10,000
Region:		  1~10
Number of Beds:   2-10
Room Type:	  1-4
View Type:	  1-4

The following is the functions are implemented.

	void initalize(int N, int mRoomCnt[])

		This function is called once in the beginning of each test case.

		N, the number of hotels, is 1,000 at most.

		mRoomCnt[] is an array that passes the number of rooms in each hotel.

		mRoomCnt[k] is the number of rooms in a hotel whose Hotel ID is k+1. (0 ≤ k ≤N-1)

		Parameters

		N: The number of hotels (1 ≤ N ≤ 1,000)

		mRoomCnt: The number of rooms in each hotel. The value is greater or equal to 1 but 100 at most.

	void addRoom (int mHotelID, int mRoomID, int mRoomInfo[])

		This function adds a new room in a hotel.

		The value of Hotel ID where a room will be added is mHotelID.

		The value of Room ID to be added is mRoomID.

		mRoomInfo is the information about a room that will be added.

		mRoomInfo is an array whose length is 5. Each index contains the following values.
		[0]: Region, [1]: Number of Beds, [2] Room type, [3]: View Type, [4]: Price

		The value of each array meets the constraints stated herein.

		Parameters

		mHotelID: The Hotel ID where a room will be added (1 ≤ mHotellDs ≤ N)

		mRoomID: The Room ID (1 ≤ mRoomID ≤ 100,000)

		mRoomInfo: The room information

	int findRoom(int mFilter[])

		This function finds and books a room.

		mFilter is an array that contains filter options.

		[0]: Check-in Date, [1]: Check-out Date, [2] : Region, [3]: Number of Beds, [4]: Room Type, [5]: View Type

		The value of each array meets the constraints stated herein.

		You cannot book a room that is already booked from the check-in date to the check-out date. Howeve it is possible for another customer to check in on the check-out date. Among the rooms that match the filter options, book the cheapest room. When the price is the same, choose the room whose ID value is the smallest.

		This function returns the ID value of a room that is booked.

		When there is NO room that can be booked, this function returns -1.

		Parameters

		mFilter: The filter options of room
		Return
		The ID value of a room that is booked

	int riseCosts(int mHotelID, int mRise)

		This function raises the prices of all rooms in a hotel by mRise%.

		Parameter

		mHotellD: The Hotel ID whose price increases (1 mHotellDs N)

		Return

		The sum of prices of all the rooms in a hotel