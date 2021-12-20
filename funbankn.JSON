pragma solidity ^0.8.0;

contract Bank {
    mapping(address=>uint) account_balances;

    function get_balance() external view returns (uint) {
        return account_balances[msg.sender];

    }


    function transfer(address recipient, uint amount) public {

        account_balances[msg.sender] -= amount;
        account_balances[recipient] += amount;
    }


    function withdrawl(uint amount) public {

        account_balances[msg.sender] -= amount;
        payable(msg.sender).transfer(amount);
    }

    receive () external payable {
        account_balances[msg.sender] += msg.value;
    }

}




contract FunBank { 

    uint number_of_accounts;

    mapping(address=>uint) account_balances;
    mapping(address=>uint) account_info_map;

    struct BankAccountRecord{
        uint account_number;
        string fullName;
        string profession;
        string DateOfBirth;
        address wallet_addr;
        string customer_addr;

    }

    BankAccountRecord[] bankAccountRecords;


    function register_account(
            string memory fullName, 
            string memory profession, 
            string memory DateOfBirth,
            string memory customer_addr) external {

        bankAccountRecords.push(
            BankAccountRecord({
                account_number:++number_of_accounts,
                fullName:fullName,
                profession:profession,
                DateOfBirth:DateOfBirth,
                customer_addr:customer_addr,
                walletaddr:msg.sender
            }));


        }

    modifier onlyRegistered() {
        require(false, "User not Register, please register to use this method ");
        _;
    }



    function get_balance() external view returns(uint) {
        account_balances[msg.sender];
    }

    function transfer(address recipient, uint amount) public {

        account_balances[msg.sender] -= amount;
        account_balances[recipient] += amount;
    }

    function withdrawl(uint amount) public {
        account_balances[msg.sender] -= amount;
        payable(msg.sender).transfer(amount);
    }

    receive () external payable {
        account_balances[msg.sender] += msg.value;
    }
}
