

contract CourseCompletionBadges {
    
    struct Badge {
        uint256 badgeId;
        string courseName;
        string badgeName;
        address awardedTo;
        uint256 dateAwarded;
    }

    address public owner;
    uint256 public badgeCounter;
    mapping(address => Badge[]) public studentBadges;

    event BadgeAwarded(address indexed student, uint256 badgeId, string courseName, string badgeName, uint256 dateAwarded);

    modifier onlyOwner() {
        require(msg.sender == owner, "Not authorized");
        _;
    }

    constructor() {
        owner = msg.sender;
        badgeCounter = 0;
    }

    function awardBadge(address student, string memory courseName, string memory badgeName) public onlyOwner {
        badgeCounter++;
        Badge memory newBadge = Badge({
            badgeId: badgeCounter,
            courseName: courseName,
            badgeName: badgeName,
            awardedTo: student,
            dateAwarded: block.timestamp
        });

        studentBadges[student].push(newBadge);

        emit BadgeAwarded(student, badgeCounter, courseName, badgeName, block.timestamp);
    }

    function getStudentBadges(address student) public view returns (Badge[] memory) {
        return studentBadges[student];
    }

    function getBadgeDetails(address student, uint256 badgeId) public view returns (Badge memory) {
        Badge[] memory badges = studentBadges[student];
        for (uint256 i = 0; i < badges.length; i++) {
            if (badges[i].badgeId == badgeId) {
                return badges[i];
            }
        }
        revert("Badge not found");
    }
}
deployment:
contract address:0x64d6049e9e2934b00bcbf096e6fbeef62479bb65
<img width="960" alt="image" src="https://github.com/user-attachments/assets/a90cd390-37ed-4dda-a24d-b141d781e563">
